# 下载指南

使用Expo开发app需要两种工具：本地开发工具和用于打开app的移动客户端。

### 本地开发工具：Expo CLI
---

Expo CLI是使用Expo开发app的工具。 除了命令行界面（CLI），Expo还具有图形用户界面，即Expo开发者工具，可在您的Web浏览器中弹出。 使用Expo Dev Tools，您可以快速设置测试设备，查看日志等。

您需要在计算机上安装Node.js（我们建议使用版本10-但8或更新的稳定版本）。 下载Node.js的[推荐版本](https://nodejs.org/en/)。 此外，您需要Git使用Expo CLI创建新项目。 你可以从这里[下载Git](https://git-scm.com/)。

您可以通过运行以下命令安装Expo CLI：
```js
 npm install -g expo-cli  
```

### 移动客户端：适用于iOS和Android的Expo
---

Expo客户端可帮助您在开发项目时查看项目。 使用Expo CLI为项目提供服务时，它会生成一个开发URL，您可以在Expo客户端中打开该URL以预览您的app。 在Android上，Expo客户端也可用于在[expo.io](https://expo.io/)上查看其他人的项目。 Expo客户端可在设备，模拟器和仿真器上运行。

#### 在您的设备上

从Play Store下载[Android版](https://play.google.com/store/apps/details?id=host.exp.exponent)或从App Store下载[iOS版](https://itunes.com/apps/exponent)

>**所需的Android和iOS版本**：Expo支持的最低Android版本是Android 5，最低iOS版本是iOS 10.0。

您无需在模拟器/模拟器上手动安装Expo客户端，因为Expo CLI将自动执行此操作。 请参阅本指南的下一部分。

#### IOS 模拟器

通过Apple App Store[安装Xcode](https://apps.apple.com/app/xcode/id497799835)。 这需要一段时间，小睡一会儿。 接下来，打开Xcode，转到首选项并单击“组件”选项卡，从列表中安装模拟器。

一旦模拟器打开并且您在Expo Dev Tools中打开了一个项目，您可以在Expo Dev Tools中按iOS模拟器上的Run，它会将Expo客户端安装到模拟器并在其中打开您的app。

> **Not Working?**  有时，Expo CLI将无法自动安装Expo客户端，这通常是由于环境或Xcode工具链中的微小差异造成的。 如果需要手动在模拟器上安装Expo客户端，可以按照以下步骤操作：
>
> * [下载](http://expo.io/--/api/v2/versions/download-ios-simulator-build)最新的模拟器版本.
> * 提取存档的内容：```mkdir Exponent-X.XX.X.app && tar xvf Exponent-X.XX.X.tar.gz -C Exponent-X.XX.X.app。```你应该得到一个像```Exponent-X.XX.X.app```这样的目录。
> * 确保模拟器正在运行
> * 在终端上，运行```xcrun simctl install booted[指向Exponent-X.XX.X.app的路径]```。

#### android 模拟器

按照我们的[Android Studio]()模拟器指南设置Android工具并创建虚拟设备。 准备好后启动虚拟设备。

一旦模拟器打开并且您在Expo Dev Tools中打开了一个项目，您可以在Expo Dev Tools中按Android设备/模拟器上的Run，它会将Expo客户端安装到模拟器并在其中打开您的app。

### Watchman
---
如果某些macOS用户未在其计算机上安装Watchman，则会遇到问题，因此我们建议您安装Watchman。 Watchman在更改时监视文件和记录，然后触发响应此操作，并由React Native在内部使用。 [下载并安装Watchman](https://facebook.github.io/watchman/docs/install.html)。