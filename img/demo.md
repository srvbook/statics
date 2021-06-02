## Mac下安装Flutter

### Step1:

使用终端打开~/.bash_profile(或者~/.zshrc)文件
``` bash
vim ~/.bash_profile
或者
vim ~/.zshrc
```
追加下面内容
``` bash
export PUB_HOSTED_URL=https://pub.flutter-io.cn
export FLUTTER_STORAGE_BASE_URL=https://storage.flutter-io.cn
export PATH=~/Documents/flutter/bin:$PATH
```

### Step2:
官网下载SDK
https://flutter.dev/docs/development/tools/sdk/releases?tab=macos
选择Stable（稳定版）的最新版本下载

### Step3：
把下载的压缩包，解压缩到~/Documents/flutter目录

### Step4:
执行以下几个安装
1. 安装XCode（从App Store下载安装）
2. 安装Cocoapods
   在终端执行下面命令进行安装
	``` bash 
	sudo gem install cocoapods
	````
3. 安装Android Studio （[官网下载](https://developer.android.com/studio)）
4. 打开Android Studio 在Preference > Plugins > Marketplace 中搜索 dart 和Flutter 安装搜到的插件
5. 在终端执行,所有选项都输入y，同意条款
	``` bash
	flutter doctor --android-licenses
	```
6. 如果安装了VSCode，那么需要安装Flutter插件（[插件下载地址](https://marketplace.visualstudio.com/items?itemName=Dart-Code.flutter)）
7. 在Xcode中打开Simulator，Open Developer Tool > Simulator
8. 在Android Studio中打开Virtual Device，Configure > AVD Manager
9. 在终端中执行Flutter环境检查命令
	``` bash 
	flutter doctor
	```
	执行结果参考：
	``` bash 
	Doctor summary (to see all details, run flutter doctor -v):
	[✓] Flutter (Channel stable, 1.22.3, on macOS 11.2.1 20D74, locale
		zh-Hans-CN)
	[✓] Android toolchain - develop for Android devices (Android SDK version
		30.0.3)
	[✓] Xcode - develop for iOS and macOS (Xcode 12.4)
	[!] Android Studio (version 4.1)
		✗ Flutter plugin not installed; this adds Flutter specific functionality.
		✗ Dart plugin not installed; this adds Dart specific functionality.
	[✓] VS Code (version 1.53.2)
	[✓] Connected device (1 available)
	```
	✓代表通过检查的项目
	✗代表需要安装的项目

PS：如果遇到参考结果的x问题，并确定已经安装Flutter和Dart的插件，那么在终端执行下面命令
``` bash
ln -s ~/Library/Application\ Support/Google/AndroidStudio4.1/plugins ~/Library/Application\ Support/AndroidStudio4.1
```
然后再次在终端执行 flutter doctor 确认结果，如果全部变为✓，那么环境就搭建完成了。