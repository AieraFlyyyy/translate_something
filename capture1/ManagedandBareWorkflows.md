# 托管(Managed)和裸露(Bare)工作流

您使用Expo工具的两种方式称为“托管”(Managed)和“裸露”(Bare)工作流。

### 托管(Managed)工作流
---
使用[expo-cli]()，移动设备上的Expo客户端以及我们的各种服务:（[推送通知]()，[构建服务]()和[无线（OTA）更新]()）。使用托管工作流构建app。 Expo尽可能地为您管理构建app的复杂性，因此我们将其称为托管工作流程。 使用托管工作流的开发人员不使用Xcode或Android Studio，他们只是通过[app.json]()编写JavaScript代码和托管配置。 在以这种方式构建app时应该考虑一些权衡，请查看[为什么是Expo?](/capture1/WhynotExpo.md) 了解更多。


### 裸露(Bare)工作流
---
裸露的app为开发人员提供了完全控制，以及随之而来的复杂性。 您可以在Expo SDK中使用大多数API，您只需手动安装和配置它们，而不是让它们为您提供开箱即用的服务。 如果您使用此工作流程，大多数Expo文档将不适用于构建您的app，而是您可以参考面向本机iOS和Android app以及React Native的教程和指南。