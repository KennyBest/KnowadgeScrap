1. 定义属性不能以new或者copy开头，否则会报
```
Property follows Cocoa naming convention for returning 'owned' objects.
```

2. 设置label高度时不能以字体大小设置高度，当label内容中包含gjyq时底部会被截取一下。
    设置高度的四种方式:

      ```
        // 方法1
        CGSize suggestedSize = [lb sizeThatFits:CGSizeMake(100, 30)];

        // 方法2
        [lb sizeToFit];
        // 方法3
        boundsWithSize

        // 方法4
        sizeWithAttributes
      ```
      高度值也不是在字体大小上随意加一个高度值，方法1和方法2 计算出来的高度一样， 方法3和方法4出来的高度一样
3.  使用`systemLayoutSizeFittingSize:`获取view的约束下的实际高度
    这里其实分为UIViewController 和 UIView两种情况处理，
      *  UIViewController中在`-viewDidLayoutSubViews`中可以获取控件的实际`frame`，
        `-ViewDidLayoutSubViews`的执行顺序晚于`- viewWillAppear`，高于`- viewDidAppear`。
      *  UIView中可以在`-layoutSubViews`和drawRect中获取

4. 当你在一个类中同时对一个属性重写setter和getter方法时，此时编译器是不会自动为当前属性创建以`_`开头的实例变量的，所以在setter方法里面使用实例变量将会报错。
解决方法：手动增加此属性的实例变量

```
@interface Person : NSObject

@property (copy, nonatomic) NSString *name;

@end

@implementation Person {
    NSString *_name;
}

- (void)setName:(NSString *)name {
    _name = name;
}

- (NSString *)name {
    return _name;
}
Â
@end
```
### 5.Window的级别只有3中，

```
UIWindow *window = [[[UIApplication sharedApplication] delegate] window];
   NSArray *windows = [UIApplication sharedApplication].windows;
   for (id windowView in windows) {
       NSString *viewName = NSStringFromClass([windowView class]);
       if ([@"UIRemoteKeyboardWindow" isEqualToString:viewName]) {
           window = windowView;
           break;
       }
   }

```
### 6.statusBar设置

```
  View controller-based status bar appearance  
  在info.plist中设置这个字段 控制statusBar的控制者  不添加时默认为YES
  YES时，viewController的配置优先级高于UIApplication的配置
  NO时， UIApplication的配置优先级高
```

### 7. CALayer的contents设置
在CALayer的contents赋值时一定是CGImage对象，并且需要用`__bridge id`桥转以下。直接用UIImage赋值时不报错，但是会得到一个空白图层。

```
UIImage *logoImage = [[UIImage imageNamed:@"logo"]  imageWithRenderingMode:UIImageRenderingModeAlwaysOriginal];
 _logoLayer.contents = (__bridge id _Nullable)(logoImage.CGImage);

```  
### 8. UITableView中获取复用cell

没有注册cell，直接crash。
```
let cell = tableView.dequeueReusableCell(withIdentifier: "KennyBest", for: indexPath)
```

如果在调用之前没有注册cell，cell会返回nil。

```
var cell = tableView.dequeueReusableCell(withIdentifier: "reuseIdentifier") as UITableViewCell?
```  
### 9. translatesAutoresizingMaskIntoConstraints

记录一下使用这个属性出现的问题，我在代码中设置`translatesAutoresizingMaskIntoConstraints`为`NO`时，在iOS9及其以上系统中没事，在iOS8上则加载不出来界面，并且会报一系列的约束冲突警告。  
官方的api是这样定义的[查看](https://developer.apple.com/documentation/uikit/uiview/1622572-translatesautoresizingmaskintoco):决定在自动布局约束中是否转变视图自适应大小标记的布尔值。  
如果这个属性被设置为`true`的时，系统会通过视图自适应标记创建一系列的约束来复制特定的行为。这也可以让你使用视图的`frame`、`bounds`、`center`来修改视图大小和位置，也可以让你在自动布局中创建一个静态基于frame的布局。  
注意自适应标记约束充分地明确了视图的大小和位置，因此不需要添加额外的约束来改变尺寸和位置，否则会产生冲突。如果你想使用自动布局来动态计算大小和位置，你必须设置这个属性为`false`，然后提供无歧义的无冲突的约束。  
对于你用程序创建的任何视图这个属性默认被设为`true`，如果在IB文件中添加的视图，系统会自动将这个属性设置为`false`。  

### 10. 请求常出现的错误
|ErrorCode|描述|
|:-----|:------|
|NSURLErrorTimedOut(-1001)|请求超时|
|NSURLErrorCannotFindHost(-1003)|找不到主机|
|NSURLErrorCannotToHost(-1004)|主机创建不了连接|
|NSURLErrorNetworkConnectionLost(-1005)|网络请求丢失|
|NSURLErrorNotConnectedToInternet(-1009)|设备不能连接网络|
|NSURLErrorUserCancelledAuthentication(-1012)|用户取消了认证|
|NSURLErrorSecureConnectionFailed(-1200)|因为未知的原因安全连接失败|  

### 11. 导航栏设置为不透明时修改view的起点  

自iOS7.0后，导航栏默认是半透明的，此时整个屏幕的坐标起点是在屏幕的左上角开始。通常会通过设置`edgesForExtendedLayout`为`UIRectEdgeNone`来控制起点从导航栏下面开始计算。那么导航栏不透明的时候坐标系的起点则默认从导航栏下的左上角开始算起。这个时候想让起点依然从整个屏幕的起点开始计算的话可以设置`extendedLayoutIncludesOpaqueBars`为`YES`来实现。
> `extendedLayoutIncludesOpaqueBars`默认为`NO`，且iOS7.0之后才可使用。

### 12. 测试PullRequest
