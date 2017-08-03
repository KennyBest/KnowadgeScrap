1. 使用QQ分享时 使用`QQApiURLObject`可以打开QQ，但是没有分享内容提示，此时，使用其它分享类即可。



## Xcode错误

### Xcode提示连接模拟器错误
  问题：提示“Software caused connection abort”
  解决：
  * 打开Xcode->Preferences->Locations->改变Command Lind Tools版本为当前使用的Xcode版本
  * 命令行执行`sudo xcode-select --switch /Applications/your_custom_folder_if_needed/Xcode.app`
