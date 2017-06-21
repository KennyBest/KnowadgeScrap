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
