# awesome-env-config-cn
各种开发语言项目环境国内（中国国内加速镜像）配置教程和部分实践经验，包括github.com, nodejs，npm，nvm, yarn, java, maven, gradle


# TODO 待补充的
欢迎大家一起补充
* python，pip，miniAnaconda, Anaconda
* msys2, mingw64, qt
* ...
# **目录**
* [github镜像](#github)
* [nodejs镜像](#nodejs)
	* [nvm nodejs版本管理工具](#nvm) 
	* [yarn nodejs包管理工具](#yarn) 
	* [npm nodejs包管理工具](#npm) 
* [java JDK](#jdk)
    * [maven包管理](#maven)
    * [gradle包管理](#gradle)
    
    
---- 

## github
* [**推荐使用chrome插件** https://github.com/jadezi/github-accelerator/ 访问github对应的网站自动展示加速连接](https://github.com/jadezi/github-accelerator/)
    * 国内镜像源1，**推荐**：[https://hub.fastgit.org](https://hub.fastgit.org)
    * 国内镜像源2：[https://github.com.cnpmjs.org 这个没有上面的快点](https://github.com.cnpmjs.org)

## nodejs
* nodejs 安装

    [镜像源：npm.taobao.com](https://developer.aliyun.com/mirror/NPM) 
    
    [官方地址：nodejs.org](nodejs.org)
    
    * 直接下载安装（**推荐使用nvm管理nodejs版本自由切换**）：
    
        * 下载地址： [http://npm.taobao.org/mirrors/node](http://npm.taobao.org/mirrors/node) 选择对应的版本下载安装即可

* [nodejs 配置国内npm源，参考npm nodejs包管理工具配置](#npm)

## nvm
* linux或者mac

    [镜像源：https://hub.fastgit.org/nvm-sh/nvm](https://hub.fastgit.org/nvm-sh/nvm) 
    
    [官方地址：https://github.com/nvm-sh/nvm](https://github.com/nvm-sh/nvm)
    
    * 安装
        * linux或者mac安装，镜像：
             ```bash
                curl -o- https://raw.fastgit.org/nvm-sh/nvm/master/install.sh | bash
                或者
                wget -qO- https://raw.fastgit.org/nvm-sh/nvm/master/install.sh | bash
             ```
        * linux或者mac安装，官方：
             ```bash
                curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.35.3/install.sh | bash
                或者
                wget -qO- https://raw.githubusercontent.com/nvm-sh/nvm/v0.35.3/install.sh | bash
             ```
    * 配置国内源
        * 设置环境变量：NVM_NODEJS_ORG_MIRROR，bash编辑~/.bashrc，zsh编辑~/.zshrc
        ```bash
            export NVM_NODEJS_ORG_MIRROR=http://npm.taobao.org/mirrors/node
        ```
    
* windows 

    [镜像源：https://hub.fastgit.org/coreybutler/nvm-windows](https://hub.fastgit.org/coreybutler/nvm-windows) 
    
    [官方推荐地址：https://github.com/coreybutler/nvm-windows](https://github.com/coreybutler/nvm-windows)
    
    * 安装
        * 镜像：
             [https://hub.fastgit.org/coreybutler/nvm-windows/releases 下载最新的版本](https://hub.fastgit.org/coreybutler/nvm-windows/releases)
        * 官方：
             [https://github.com/coreybutler/nvm-windows/releases/ 下载最新的版本](https://github.com/coreybutler/nvm-windows/releases/)
    
    * 配置国内源
        * 设置
        ```cmd
            nvm node_mirror http://npm.taobao.org/mirrors/node
            nvm npm_mirror https://npm.taobao.org/mirrors/npm/
        ```
    
## yarn
* yarn 安装

    [官方地址：https://yarnpkg.com/](https://yarnpkg.com/)

    * 需要首先安装[nodejs](#nodejs)
    * 然后使用npm安装yarn或者更新
        ```cmd
        npm i -g yarn 
        或者
        npm install -g yarn 
       ```
* 配置国内源
    ```cmd
    yarn config set registry https://registry.npm.taobao.org
    ```

## npm 

* npm 默认安装nodejs后就已经有了，使用以下命令查看
    ```cmd
    npm -v
    ```
* npm更新，一下不适用于nvm安装的node
    ```cmd
    npm i -g npm 
    ```
* 配置国内源，最简单的一种方式，自动配置淘宝源中多个配置
    ```cmd
    npm install -g mirror-config-china
    ```
## jdk
* java jdk 安装
    * [华为镜像，oracle的jdk有商业版权，没有最新版本下载 https://repo.huaweicloud.com/java/jdk/](https://repo.huaweicloud.com/java/jdk/) 
    * [官方下载速度不慢，目前需要注册登录oracle账号才能下载(百度搜索：jdk下载账号) https://www.oracle.com/cn/java/](https://www.oracle.com/cn/java/) 
    * [openjdk 镜像下载有很很多，比如清华 https://mirrors.tuna.tsinghua.edu.cn/AdoptOpenJDK](https://mirrors.tuna.tsinghua.edu.cn/AdoptOpenJDK)
* 配置现在一般都不需要配置

## maven
* [maven安装，apache比较良心，下载相关的基本都自带镜像 http://maven.apache.org/download.cgi](http://maven.apache.org/download.cgi)
    
    * [在此页面下载，默认自动选择最快的镜像 http://maven.apache.org/download.cgi](http://maven.apache.org/download.cgi)
    
* 配置国内源
    * [打开 maven 的配置文件（ windows 机器一般在 maven 安装目录的 conf/settings.xml 或者用户目录下.m2/setting.xml ），在<mirrors></mirrors>标签中添加 mirror 子节点, https://maven.aliyun.com/mvn/guide](https://maven.aliyun.com/mvn/guide)
    ```xml
    <mirror>
      <id>alimaven</id>
      <name>aliyun maven</name>
      <url>https://maven.aliyun.com/repository/public</url>
      <mirrorOf>central</mirrorOf>
    </mirror>

    <mirror>
      <id>jcenter</id>
      <name>jcenter</name>
      <url>https://maven.aliyun.com/repository/central</url>
      <mirrorOf>central</mirrorOf>
    </mirror>

    <mirror>
      <id>google</id>
      <name>google</name>
      <url>https://maven.aliyun.com/repository/google</url>
      <mirrorOf>central</mirrorOf>
    </mirror>

    <mirror>
      <id>spring</id>
      <name>aliyun maven spring</name>
      <url>https://maven.aliyun.com/repository/spring</url>
      <mirrorOf>central</mirrorOf>
    </mirror>

    <mirror>
      <id>spring-plugin</id>
      <name>aliyun maven spring-plugin</name>
      <url>https://maven.aliyun.com/repository/spring-plugin</url>
      <mirrorOf>central</mirrorOf>
    </mirror>

    <mirror>
      <id>gradle-plugin</id>
      <name>aliyun maven gradle-plugin</name>
      <url>https://maven.aliyun.com/repository/gradle-plugin</url>
      <mirrorOf>central</mirrorOf>
    </mirror>

    <mirror>
      <id>grails-core</id>
      <name>aliyun maven grails-core</name>
      <url>https://maven.aliyun.com/repository/grails-core</url>
      <mirrorOf>central</mirrorOf>
    </mirror>

    <mirror>
      <id>apache snapshots</id>
      <name>aliyun maven apache snapshots</name>
      <url>https://maven.aliyun.com/repository/apache-snapshots</url>
      <mirrorOf>central</mirrorOf>
    </mirror>

    ```
## gradle 
* gradle 安装 

    * 镜像，目前没有查询到国内下载gradle镜像的地址，大家知道的欢迎提供
    * [官网 https://services.gradle.org/distributions/](https://services.gradle.org/distributions/)
* gradle 配置
    
    终极配置，在用户目录下~/.gradle/目录下增加init.gradle文件，内容如下
    ```groovy
     allprojects {
     	buildscript {
     		repositories {
     			mavenLocal()
     			def NEXUS_URL = 'https://maven.aliyun.com/repository/public'
     			def jcenter_URL = 'https://maven.aliyun.com/repository/jcenter'
     			def m2_URL = 'https://maven.aliyun.com/repository/gradle-plugin'
     			def spring_plugin_URL = 'https://maven.aliyun.com/repository/spring-plugin'
     			def spring_URL = 'https://maven.aliyun.com/repository/spring'
     			def GOOGLE_URL = 'https://maven.aliyun.com/repository/google'
     			all { ArtifactRepository repo ->
     				if(repo instanceof MavenArtifactRepository){
     					def url = repo.url.toString()
     					if (url.startsWith('https://repo1.maven.org/maven2') || url.startsWith('https://jcenter.bintray.com') || 		url.startsWith('http://mirrors.ibiblio.org')) {
     						project.logger.lifecycle "Repository ${repo.url} replaced by $jcenter_URL."
     						remove repo
     					} else if (url.startsWith('https://plugins.gradle.org/m2/')) {
     						project.logger.lifecycle "Repository ${repo.url} replaced by $m2_URL."
     						remove repo
     					} else if (url.startsWith('http://repo.spring.io/libs-milestone/')) {
     						project.logger.lifecycle "Repository ${repo.url} replaced by $spring_URL."
     						remove repo
     					} else if (url.startsWith('http://repo.spring.io/plugins-release/')) {
     						project.logger.lifecycle "Repository ${repo.url} replaced by $spring_plugin_URL."
     						remove repo
                        // 这里是安卓相关下载的加速，本地没有出现下载慢的情况，所以这个就屏蔽了
     					//}else if (url.startsWith('https://dl.google.com/dl/android/maven2/')) {
     					//	project.logger.lifecycle "Repository ${repo.url} replaced by $GOOGLE_URL."
     					//	println("buildscript ${repo.url} replaced by $GOOGLE_URL.")
     					//	remove repo
     					}
     				}
     			}
     			
     			maven { url 'https://maven.aliyun.com/repository/public' }
     			maven { url 'https://maven.aliyun.com/repository/spring' }
     			maven { url 'https://maven.aliyun.com/repository/spring-plugin' }
     			maven { url "https://maven.aliyun.com/repository/grails-core" }
     			maven { url "https://maven.aliyun.com/repository/apache-snapshots" }
     			maven { url "https://maven.aliyun.com/repository/gradle-plugin" }
     			maven { url 'https://maven.aliyun.com/repository/google' }
     			jcenter {
     				url jcenter_URL
     			}
     			maven {
     				url NEXUS_URL
     			}
     		}
     	
     	}
         repositories {
             mavenLocal()
     		def NEXUS_URL = 'https://maven.aliyun.com/repository/public'
     		def jcenter_URL = 'https://maven.aliyun.com/repository/jcenter'
     		def m2_URL = 'https://maven.aliyun.com/repository/gradle-plugin'
     		def spring_plugin_URL = 'https://maven.aliyun.com/repository/spring-plugin'
     		def spring_URL = 'https://maven.aliyun.com/repository/spring'
     		def GOOGLE_URL = 'https://maven.aliyun.com/repository/google'
             all { ArtifactRepository repo ->
                 if(repo instanceof MavenArtifactRepository){
                     def url = repo.url.toString()
                     if (url.startsWith('https://repo1.maven.org/maven2') || url.startsWith('https://jcenter.bintray.com') || 		url.startsWith('http://mirrors.ibiblio.org')) {
                         project.logger.lifecycle "Repository ${repo.url} replaced by $jcenter_URL."
                         remove repo
                     } else if (url.startsWith('https://plugins.gradle.org/m2/')) {
                         project.logger.lifecycle "Repository ${repo.url} replaced by $m2_URL."
                         remove repo
                     } else if (url.startsWith('http://repo.spring.io/libs-milestone/')) {
                         project.logger.lifecycle "Repository ${repo.url} replaced by $spring_URL."
                         remove repo
                     } else if (url.startsWith('http://repo.spring.io/plugins-release/')) {
                         project.logger.lifecycle "Repository ${repo.url} replaced by $spring_plugin_URL."
                         remove repo
                    // 这里是安卓相关下载的加速，本地没有出现下载慢的情况，所以这个就屏蔽了
                    //}else if (url.startsWith('https://dl.google.com/dl/android/maven2/')) {
     				//	project.logger.lifecycle "Repository ${repo.url} replaced by $GOOGLE_URL."
     				//	println("buildscript ${repo.url} replaced by $GOOGLE_URL.")
     				//	remove repo
     				}
                 }
             }
             
     		maven { url 'https://maven.aliyun.com/repository/public' }
             maven { url 'https://maven.aliyun.com/repository/spring' }
             maven { url 'https://maven.aliyun.com/repository/spring-plugin' }
     		maven { url "https://maven.aliyun.com/repository/grails-core" }
             maven { url "https://maven.aliyun.com/repository/apache-snapshots" }
             maven { url "https://maven.aliyun.com/repository/gradle-plugin" }
     		maven { url 'https://maven.aliyun.com/repository/google' }
             jcenter {
     			url jcenter_URL
     		}
     		maven {
     			url NEXUS_URL
     		}
         }
     }

    ```
