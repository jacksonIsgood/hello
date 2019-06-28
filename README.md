# 谷歌常见错误调试信息解决方案

1.Unchecked runtime.lastError: The message port closed before a response was received.

这类问题一般是由于浏览器拓展工具打开导致的可以在程序调试之前将其关闭。

2.[HMR] Waiting for update signal from WDS...

将这里的信息翻译过来是 ：来自 WDS 的提示，正在等待更新。 好了在解释这个意思之前需要知道几个概念 ：
    
    1、什么是webpack ：
    webpack是一个自动化构建工具，意在帮前端开发者解决除了业务开发外的杂事，比如：打包、语言的转换、热更新、启本地服务器等等。与本问题相关的webpack配     置是它为我们搭建的本地服务器以及热更新功能。

    2、[HMR] 是什么：
    它是 Hot Module Replacement 的简写。翻译过来：模块热更新。所以HDR开头的信息提示由webpack/hot/dev-server模块产生。

    3、[WDS] 是什么：
    它是 Webpack dev Server 的简写。翻译过来：webpack的开发环境服务器（本地服务器）。所以WDS开头的信息提示由 webpack-dev-server本地服务器产生

3.[WDS] Warnings while compiling. 
编译时出现警告

4.vue报错:There are multiple modules with names that only differ in casing.
1 、在引用组件时，路径大小写不对也会造成此报错
2 、在组件使用vuex时，引用vuex大小写错误
