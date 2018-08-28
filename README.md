# Retrofit

## 一、简介

![image](https://github.com/3rdPartyLibraryAnalysis/Retrofit/blob/master/one.png)

特别注意：

   准确来说，Retrofit 是一个 RESTful 的 HTTP 网络请求框架的封装。 
  
   原因：网络请求的工作本质上是 OkHttp 完成，而 Retrofit 仅负责 网络请求接口的封装
      
![image](https://github.com/3rdPartyLibraryAnalysis/Retrofit/blob/master/two.png)

App应用程序通过 Retrofit 请求网络，实际上是使用 Retrofit 接口层封装请求参数、Header、Url 等信息，之后由 OkHttp 完成后续的请求操作

在服务端返回数据之后，OkHttp 将原始的结果交给 Retrofit，Retrofit根据用户的需求对结果进行解析


## 二、使用
 
   使用 Retrofit 的步骤共有7个：

步骤1：添加Retrofit库的依赖 

步骤2：创建 接收服务器返回数据 的类 

步骤3：创建 用于描述网络请求 的接口

步骤4：创建 Retrofit 实例 

步骤5：创建 网络请求接口实例 并 配置网络请求参数 

步骤6：发送网络请求（异步 / 同步）
  
  ### 步骤1：添加Retrofit库的依赖
  
  1. 在 Gradle加入Retrofit库的依赖

   由于Retrofit是基于OkHttp，所以还需要添加OkHttp库依赖

build.gradle

dependencies {
    compile 'com.squareup.retrofit2:retrofit:2.0.2'
    // Retrofit库
    compile 'com.squareup.okhttp3:okhttp:3.1.2'
    // Okhttp库
  }

 2. 添加 网络权限 
  AndroidManifest.xml

<uses-permission android:name="android.permission.INTERNET"/>
