# TXPush
腾讯云推送
### 1. Android SDK 集成指南
#### 1.1.1. 导入依赖
AndroidStudio 上可以使用 jcenter 远程仓库自动接入，不需要在项目中导入jar包和so文件； 在 AndroidManifest.xml 中不需要配置信鸽相关的内容，jcenter 会自动导入。 导入依赖过后修改应用配置，书写注册代码就能够实现信鸽快速接入。 对应的依赖版本号均是官网上最新的版本。 用户自定义的recevier.依然需要在Androidmanifest.xml配置相关节点。
在app build.gradle文件下配置 以下内容
