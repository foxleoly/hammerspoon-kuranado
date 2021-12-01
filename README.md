[TOC]

## 使用
```
cd ~/.hammerspoon
git clone https://github.com/KURANADO2/hammerspoon-kuranado.git
mv hammerspoon-kuranado/* .
mv hammerspoon-kuranado/.git .
mv hammerspoon-kuranado/.gitignore .
```

## 本工程提供功能
### 窗口移动

替代 Magnet 进行窗口移动

![](./images/window.png)

### 应用切换

为应用配置快捷键，比 ⌘⇥ 和 Alfred 切换程序更高效（建议只为高频使用的一些软件分配快捷键）

### 实时网速显示

替代 NetWorker Pro 实时显示网速（每两秒刷新一次）

![](./images/network.png)

### 密码粘贴

解决某些网站禁止粘贴密码问题

### 快捷键列表查看

任意界面下按 ⌥/ 显示/隐藏快捷键列表

![](./images/shortcut.png)

### 下班提醒

每天 18:00 提醒下班（根据实际下班时间自行修改脚本），鼠标点击可关闭动画

![](./images/after-work.png)

## 快捷键列表

请根据需要自行修改

快捷键|功能
-|-
⌃⌥←|左半屏
⌃⌥→|右半屏
⌃⌥↑|上半屏
⌃⌥↓|下半屏
⌃⌥U|左上角
⌃⌥I|右上角
⌃⌥J|左下角
⌃⌥K|右下角
⌃⌥1|1/9
⌃⌥2|2/9
⌃⌥3|3/9
⌃⌥4|4/9
⌃⌥5|5/9
⌃⌥6|6/9
⌃⌥7|7/9
⌃⌥8|8/9
⌃⌥9|9/9
⌃⌥C|居中
⌃⌥D|左 1/3（横屏）或上 1/3（竖屏）
⌃⌥F|中 1/3
⌃⌥G|右 1/3（横屏）或下 1/3（竖屏）
⌃⌥E|左 2/3（横屏）或上 2/3（竖屏）
⌃⌥T|右 2/3（横屏）或下 2/3（竖屏）
⌃⌥=|等比例放大窗口
⌃⌥-|等比例缩小窗口
⌃⌥↩︎|最大化
⌃⌥⌘←|窗口由主屏移动到副屏
⌃⌥⌘→|窗口由副屏移动到主屏
⌥Q|打开 QQ
⌥W|打开 WeChat
⌥V|打开 Visual Studio Code
⌥F|打开 Finder
⌥C|打开 Chrome
⌥J|打开 Intellij IDEA
⌥N|打开 WizNote
⌥G|打开 Gridea
⌥D|打开 DataGrip
⌥T|打开 iTerm2
⌥M|打开 Foxmail
⌥P|打开 Postman
⌥O|打开 Word
⌥E|打开 Excel
⌥S|打开 SecureCRT
⌥Y|打开 PyCharm
⌥R|打开 Another Redis Desktop Manager
⌃⌘V|以模拟按键方式将剪贴板中的字符粘贴出来（解决某些网站禁止粘贴密码问题）
⌥/|显示/隐藏快捷键列表

**注意：**屏幕之间移动窗口，需要保证主屏在右侧，副屏在左侧，这里的左侧、右侧指的是显示器的逻辑位置，而不是物理位置，当然一般大家都会保证逻辑位置和物理位置一致，以方便操作。所谓的逻辑位置，可在：系统偏好设置 -> 显示器 -> 排列 下设置：

![image](./images/monitor.png)

我有两台显示器，一台放在桌子的左边，一台放在桌子的右边，这就是物理位置。为了操作方便，如上图，我将实际桌子上左边的显示器排列在左边，桌子上右边的显示器排列在右边，这样就保证了物理位置和逻辑位置是一致的，同时将上图中的白色条块拖动到右侧显示器上，用于标识右侧的显示器是主显示器。

## 关于应用 bundle id

上面配置中使用快捷键切换应用，需要拿到应用的 bundle id（请注意 bundle id 配置到 hammerspoon 中需要区分大小写，否则 console 会报错），可通过如下方式拿到：
```
osascript -e 'id of app "Name of App"'
```

![image](./images/bundleid.png)

另外，如果你使用的是比较新的 Mac 系统，终端下输入 ls /Applications 可能是看不到系统自带应用的，如下图，ll 查看不到 Mac 自带的邮件应用，但 Finder 打开 /Applications 目录则可以看到邮件应用

![image](./images/applications.png)

此时我们可以在 Finder 中选中邮件应用，右键：显示包内容 -> Contents -> 打开 info.plist 文件，找到 CFBundleIdentifier 配置项，该配置项的值即为 bundle id，当然此方法也适应于自己安装的应用

![image](./images/mail.png)

## 参考
- [学长博客 - OSX--OSX应用快速切换方案](https://mrdear.cn/posts/osx_app_switcher.html)
- [官方 Quick Start](https://www.hammerspoon.org/go/)
- [官方文档](http://www.hammerspoon.org/docs/)
- [少数派 - 免费又强大的 macOS 自动化工具，Hammerspoon 可以让你少买很多 App](https://sspai.com/post/53992)
- [V2EX - 推荐一个 MacOS 上用了就无法自拔的神器](https://www.v2ex.com/t/553241)
- [Hammerspoon - 岂止于窗口管理](https://zhuanlan.zhihu.com/p/72499152)
- [hammerspoon-init](https://github.com/rtoshiro/hammerspoon-init)
- [菜鸟教程 - Lua 教程](https://www.runoob.com/lua/lua-tutorial.html)
- [Easily see any app’s bundle identifier](https://robservatory.com/easily-see-any-apps-bundle-identifier/)
- [GitHub - wangshub/hammerspoon-config](https://github.com/wangshub/hammerspoon-config)
- [GitHub - ashfinal/awesome-hammerspoon](https://github.com/ashfinal/awesome-hammerspoon)