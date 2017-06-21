## 1. GoodsAsOldPhones
* 如果用到UIScrollView时，显示的界面会超出屏幕，IB布局时，可以不将UIScrollView直接添加界面上，而是关联到对应的UIViewController中，这样方便编辑
* UIScrollView约束布局 在UIScrollView上添加一个容器view，先添加好容器view与scrollView的约束，然后在容器view中布局

## 2. LoveTweet
`Social`框架使用，以新浪微博为例：

```Objc
@IBAction func sendWeiBo(_ sender: UIButton) {
    if SLComposeViewController.isAvailable(forServiceType: SLServiceTypeSinaWeibo) {
        let vc: SLComposeViewController = SLComposeViewController(forServiceType: SLServiceTypeSinaWeibo)
        // 设置初始化文字 -可在弹出界面修改
        vc.setInitialText("test weibo content")
        // 添加图片
        vc.add(UIImage(named: "image1")!)
        // 添加URL
        vc.add(URL(string: "https://www.baidu.com"))
        // 图片 和 URL可以通过以下方法删除
        // vc.removeAllImages()
        // vc.removeAllURLs()
        // 可设置completionHandler来处理用户操作结束
        self.present(vc, animated: true, completion: nil)
    }
}

```  
目前`Social`框架定义四种社交环境

```Objc
@available(iOS 6.0, *)
public let SLServiceTypeTwitter: String
@available(iOS 6.0, *)
public let SLServiceTypeFacebook: String
@available(iOS 6.0, *)
public let SLServiceTypeSinaWeibo: String
@available(iOS 7.0, *)
public let SLServiceTypeTencentWeibo: String
```  
## 3. Stopwatch  
1. 函数共用部分的抽离，尽可能做到代码功能极致话
  ```Objc
  // MARK: reset timer seperately
  fileprivate func resetMainTimer() {
    resetTimer(mainStopwatch, label: timerLabel)
    laps.removeAll()
    lapsTableView.reloadData()
  }

  fileprivate func resetLapTimer() {
    resetTimer(lapStopwatch, label: lapTimerLabel)
  }

  fileprivate func resetTimer(_ stopwatch: Stopwatch, label: UILabel) {
    stopwatch.timer.invalidate()
    stopwatch.counter = 0.0
    label.text = "00:00:00"
  }
  ```
2. `ViewController`中的方法可以通过拓展`Selector`来使用,记得合理使用访问控制符
  ```Objc
  fileprivate extension Selector {
    static let updateMainTimer = #selector(ViewController.updateMainTimer)
    static let updateLapTimer = #selector(ViewController.updateLapTimer)
  }
  ```
## 14. SnapchatMenu

  1.
  ```
    @available(iOS 5.0, *)
    open func willMove(toParentViewController parent: UIViewController?)
  ```
  2.
  ```
    @available(iOS 5.0, *)
    open func didMove(toParentViewController parent: UIViewController?)
  ```
  在子控制器之间切换的时候这两个方法是给UIViewController子类去调用的。如果它们被重写，重写的方法一定要保证调用父类的实现。parent参数在它从其父controller中移除的时候是nil，否则就是最新的父controller。

  `addChildViewController:` 在添加子控制器之前会调用 `[child willMoveToParentViewController: self]`。然而，并不会调用 didMoveToParentViewController:。我们期望 一个容器控制器的子类在子控制器过渡后调用这个回调，或者万一没有转变，及时地调用。

  相似地，`removeFromParentViewController` 也不会在移除之前主动调用[self willMoveToParentViewController: nil]

  这个是容器子类的职责，容器子类一般定义一个方法来通过首次调用addViewController:过渡到一个新的自控制器，然后执行一个转场，最终调用didMoveToParentViewController。在移除的时候不主动调用willMoveTo， 需要手动`[child willMoveToParentViewController:nil]`。
