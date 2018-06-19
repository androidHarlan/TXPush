# TXPush
腾讯云推送
### 1. Android SDK 集成指南
#### 1.1.1. 导入依赖
AndroidStudio 上可以使用 jcenter 远程仓库自动接入，不需要在项目中导入jar包和so文件； 在 AndroidManifest.xml 中不需要配置信鸽相关的内容，jcenter 会自动导入。 导入依赖过后修改应用配置，书写注册代码就能够实现信鸽快速接入。 对应的依赖版本号均是官网上最新的版本。 用户自定义的recevier.依然需要在Androidmanifest.xml配置相关节点。</br></br>
在app build.gradle文件下配置 以下内容
~~~

    android {
        ......
        defaultConfig {

            //信鸽官网上注册的包名.注意application ID 和当前的应用包名以及 信鸽官网上注册应用的包名必须一致。
            applicationId "你的包名" 
            ......

            ndk {
                //根据需要 自行选择添加的对应cpu类型的.so库。 
                abiFilters 'armeabi', 'armeabi-v7a', 'arm64-v8a' 
                // 还可以添加 'x86', 'x86_64', 'mips', 'mips64'
            }

            manifestPlaceholders = [

                XG_ACCESS_ID:"注册应用的accessid",
                XG_ACCESS_KEY : "注册应用的accesskey",
            ]
            ......
        }
        ......
    }

    dependencies {
        ......

    //完整的信鸽依赖三个都必须有，如果发生依赖冲突请根据对应的依赖版本号选择高版本的依赖。（使用jcenter自动接入请确认libs 中没有信鸽的相关jar包）

    //信鸽3.2.3 release版本
    //完整的信鸽依赖三个都必须有，如果发生依赖冲突请根据对应的依赖版本号选择高版本的依赖。（使用jcenter自动接入请                    确认libs 中没有信鸽的相关jar包） 

    //信鸽3.2.4 beta版本
    //compile 'com.tencent.xinge:xinge:3.2.4-beta'

    //信鸽jar
    compile 'com.tencent.xinge:xinge:3.2.3-release'
    //wup包
    compile 'com.tencent.wup:wup:1.0.0.E-release'
    //mid包
    compile 'com.tencent.mid:mid:4.0.6-release'

    }
~~~
