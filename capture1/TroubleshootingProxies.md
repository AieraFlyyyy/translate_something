# 代理故障排除

### Mac OS代理配置（Sierra）
___
> 如果出现任何问题，您可以使用自动代理配置恢复到系统网络首选项中的“自动代理设置”```your-corporate-proxy-uri：port-number / proxy.pac```

#### 概览
为了在公司的Wi-Fi网络上在本地iOS模拟器中运行它，需要本地代理管理器。 这个名为[Charles](http://charlesproxy.com/)的本地代理应用程序是我们的iOS开发团队使用的。 认识Charles，结识他。 他是你的朋友。

#### 打开Mac OS网络首选项

1. 打开Mac的系统偏好设置（Apple菜单>系统偏好设置）。
2. 转到网络。
3. 确保您的```Location```设置为代理网络，而不是“自动”。
4. 在左侧/或以太网连接中选择Wi-Fi后，单击窗口右下角的高级....

#### 配置代理地址
1. 如果已设置，则禁用/取消选中“自动代理配置”。
2. 检查“Web代理（HTTP）”并将“Web代理服务器”设置为127.0.0.1：8888
3. 选中“Secure Web Proxy（HTTPS）”并将“Secure Web Proxy Server”设置为127.0.0.1：8888

#### 配置```Charles```
1.  打开查尔斯
2. 如果它要求，不要让它管理您的Mac OS网络配置，前面的步骤就是这样做的。 （如果更改Charles端口，请将上一步更新为正确的端口，而不是默认的8888）
3. 在Charles的菜单中，转到“代理”>“外部代理设置”，选中“使用外部代理服务器”
4. 检查Web代理（HTTP），然后输入your-corporate-proxy-uri：port-number
5. 检查代理服务器需要密码
6. 域名：您的域名，用户名：您的用户名，密码：您的密码
安全Web代理（HTTPS）也是如此。 
7. 请务必填写相同的代理，用户名和密码地址字段。
8. 在以下主机的旁路外部代理的文本区域中输入：
```js
localhost
*.local
```
您可能需要包含邮件服务器或其他公司网络地址。
选中“始终绕过localhost的外部代理”。

#### iOS模拟器配置
如果您现有的iOS模拟器自定义设置无效，请从菜单中选择“模拟器>重置内容和设置”。

如果您的模拟器是运行状态，请先退出。

现在，在Charles的“帮助”菜单>安装Charles Root证书，然后再次在iOS模拟器中安装Charles Root证书

>技术说明：整个过程是必需的，因为iOS模拟器提供的是bum代理证书而不是实际的证书，并且不允许使用https://exp.host/来运行Expo。
另请注意：配置需要Internet访问的应用程序（如Spotify）以使用http：// localhost：8888作为代理。 某些应用程序（例如Chrome和Firefox），您可以在设置中配置使用“系统网络首选项”，它将使用Charles：8888，或者不使用代理，具体取决于您在Apple菜单/网络中设置“位置”的方式 喜好。 如果设置为“自动”，则不使用代理，如果将其设置为“您的代理网络”，则使用代理并且Charles将需要运行。

### 命令行应用程序代理配置
___
npm，git，Brew，Curl和任何其他命令行应用程序也需要代理访问。

#### npm
打开```~/.npmrc```然后设置：
```js
http_proxy=http://localhost:8888
https_proxy=http://localhost:8888
```

#### git
打开```~/.gitconfi```然后设置：
```js
[http]
    proxy = http://localhost:8888
[https]
    proxy = http://localhost:8888
```
#### 命令行应用程序
根据你的shell和config，打开```〜/ .bashrc```，```〜/ .bash_profile```或```〜/ .zshrc```或你设置shell变量的任何地方，并设置：
```js
export HTTP_PROXY="http://localhost:8888"
export http_proxy="http://localhost:8888"
export ALL_PROXY="http://localhost:8888"
export all_proxy="http://localhost:8888"
export HTTPS_PROXY="http://localhost:8888"
export https_proxy="http://localhost:8888"
```
注意：如果您将网络位置切换回“自动”以便使用npm或git，则需要在要禁用的行之前使用```＃```注释掉这些行。 如果您愿意，也可以使用命令行代理管理器。
___