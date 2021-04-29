## 简介与教程
利用Xposed框架实现的类似于手机管家的Android系统工具。  

详细的文档与教程，请参考[WIKI](https://tornaco.github.io/X-APM/)。

[![Codacy Badge](https://api.codacy.com/project/badge/Grade/7da67140876941b784095ad44a32509f)](https://app.codacy.com/app/Tornaco/X-APM?utm_source=github.com&utm_medium=referral&utm_content=Tornaco/X-APM&utm_campaign=badger)
[![Build Status](https://travis-ci.org/Tornaco/X-APM.svg?branch=master)](https://travis-ci.org/Tornaco/X-APM)
[![Crowdin](https://d322cqt584bo4o.cloudfront.net/x-apm/localized.svg)](https://crowdin.com/project/x-apm)

重构版本：https://github.com/Tornaco/Thanox


1. 目的

    借助XPOSED实现系统级别应用管理。

1.1 功能

应用锁

    应用启动验证。
    最近任务验证。
    最近任务高斯模糊（算法来自fastblur）。
    自定义的验证器。
    闯入抓拍。
    指纹验证。

自启动管理

    限制某些（用户选择）应用的开机广播接收。

管理启动管理

    限制某些（用户选择）应用的关联启动（服务/广播）。

锁屏清理

    屏幕锁定后清理后台应用（用户可设置白名单）。

应用组件控制（开发中）

    禁用某应用的某些（用户选择）组件（服务/广播）。

2. 功能演示

参考README最下方demo视频。
3. 设计思路

系统服务Hook与Binder服务注入。

核心服务： https://github.com/Tornaco/X-APM/blob/master/app/src/main/java/github/tornaco/xposedmoduletest/xposed/service/XAshmanServiceImpl.java https://github.com/Tornaco/X-APM/blob/master/app/src/main/java/github/tornaco/xposedmoduletest/xposed/service/XAppGuardServiceImpl.java

Xposed模块代理： https://github.com/Tornaco/X-APM/blob/master/app/src/main/java/github/tornaco/xposedmoduletest/xposed/XModuleDelegate.java
4. 编译

依赖hiddenapi，Xposed-Framework。
4.1 自选编译

https://github.com/Tornaco/X-APM/tree/master/build_var_controls
5. 测试

5.1 查看最新测试报告

5.2 测试代码位于androidTest目录下。


3. 编译说明

需要替换 <SDK location>/platforms/android-26/android.jar //项目里面包含：building/hiddenapi/26/android.jar

根目录：build_var_config 文件配置需要的功能模块。
