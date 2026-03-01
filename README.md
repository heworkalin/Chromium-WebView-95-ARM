Chromium-WebView-95-ARM
 
Android System WebView 95.0.4608.0 (ARM/armeabi)
 
本项目提供从 Chromium 官方源码编译的  Android System WebView  安装包，专门针对 ARM/armeabi (ARMv5TE) 架构，并兼容 Android 5.0 (API Level 21) 及以上系统。
 
 
 
关键信息
 
- 版本：Chrome 95.0.4608.0
- 编译来源：Chromium 官方源码
- 参考文档：知乎：一文搞定Android WebView编译+AOSP集成
- 最低兼容：Android 5.0 (API 21)
- 支持架构：ARM/armeabi (ARMv5TE)
- 签名状态：V1 + V2
 
 
 
适用场景
 
- 运行 Android 5.0+ 的老旧 ARMv5 设备
- 点读笔、学习机等嵌入式设备
- 需要标准 WebView 支持的定制化安卓设备
 
 
 
使用方法
 
1. 下载  AndroidSystemWebView.armeabi.apk  文件
2. 通过 ADB 或文件管理器安装：
bash  
adb install AndroidSystemWebView.armeabi.apk
 
 
 
 
编译说明
 
本安装包严格遵循 Chromium 官方 Android Build Instructions 编译，仅通过以下 GN 参数进行架构和 API 适配，未对源码进行任何额外修改：
 
python  
gn args out/Default

target_os = "android"
target_cpu = "arm"

# 开启“官方版本”选项
is_debug = false
is_official_build = true

# 核心：设置安卓最小SDK API级别（安卓5=21），这是官方变量
chrome_public_manifest_package = "com.android.webview"

# 配套：设置NDK API级别，和SDK保持一致（必须同步）
android32_ndk_api_level = 21
android64_ndk_api_level = 21

# 关闭测试配置
disable_fieldtrial_testing_config = true

is_component_build = false

# 添加视频编解码支持
ffmpeg_branding = "Chrome"
proprietary_codecs = true

# 禁用谷歌特有的品牌/功能
is_chrome_branded = false
use_official_google_api_keys = false

# 禁用一些实验性(不稳定)功能，并隐藏WebView DevTools
android_channel = "stable"
