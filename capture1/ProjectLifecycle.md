# 项目生命周期

通过Expo，您可以轻松开始编写app，并使用托管(Managed)工作流程将其一直带到生产环境中。 以下是您可能会使用的工具和服务的概述。

本指南旨在对世博会提供的内容进行高级解释。 如果您好奇，[这里]()将更详细地介绍这些主题的技术实现。

![](https://docs.expo.io/static/images/project-lifecycle-workflows.png "Expo项目的生命周期")

### 创建一个Expo项目
---
您只需使用我们的桌面工具和文本编辑器即可创建新的Expo项目。 有关创建项目，在设备上运行项目以及进行更改的快速指南，请参阅[Up and Running]()指南。

Expo apps是内置Expo SDK的React Native app。 最快的入门方法是使用[Up and Running]()指南，但您也可以[转换现有的React Native app]()或仅将部分Expo应用到您的app中。

### 本地测试
---
当您处理托管的Expo项目时，我们会从您的本地计算机提供项目实例。 如果关闭项目或关闭计算机，则开发项目将停止。

在此期间，您使用名为[Expo 客户端](/capture1/Installation.md)的预构建iOS / Android app 测试项目。 它会要求您的计算机提供项目的本地副本（通过localhost，LAN或tunnel），下载并运行它。 您可以利用各种开发工具，例如[调试]()，[流设备日志]()，检查元素，热模块重新加载等。

### 发布你的项目
---
如果您单击Expo Dev Tools中的“发布”按钮，我们会将您应用的缩小副本上传到我们的CDN，并为您提供```expo.io/@your-username/your-app-slug```的可共享网址。

您可以立即与拥有适用于Android的Expo客户端app的任何人分享此链接。 [阅读更多关于发布的信息]()。

在iOS上，您需要使用Apple TestFlight与他人共享您的应用。

### 更新你的app
---

您可以在不中断用户的情况下继续在本地进行更改。 每当您更改并发布app时，您的新版本都会立即显示给任何拥有该链接的人。

我们经常发布[Expo SDK]()的更新。 每次更新都包含有关如何升级项目的说明。 如果您决定更新到我们SDK的较新版本，旧版本的副本将仍然可以继续工作。 用户将下载其客户支持的最新副本。

### 部署到Apple App Store和Google Play
---

当您准备好在Apple App Store和Google Play Store上正式上架您的应用程序时，Expo可以生成部署就绪的```.ipa```和```.apk```文件，这些文件已准备好提交给Apple和Google。 我们会在服务器上生成它们，因此您仍然不需要任何Apple或Google软件。 请参阅有关[分发应用程序]()的文档。

### 更改原生代码
---

您可以将应用程序一直带到App Store和Play Store，同时使用托管工作流程仅编写JS。 但是，如果您遇到Expo SDK未能满足的需求（[请参阅“为什么不参加世博会？”以帮助预测您是否会遇到此问题](/capture1/WhynotExpo.md)），我们提供弹出功能，从而为您提供原生Xcode和Android Studio 表示您的项目，以便您可以更改所需的任何内容。

**注意**：如果选择弹出，则不再提供某些Expo服务。 例如，expo-cli将无法运行，我们无法再为您生成独立版本，并且您将无法使用expo publish发布更新。 您的项目成为正常的React Native项目，其中包含大部分Expo SDK API。