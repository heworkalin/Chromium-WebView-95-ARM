# Chromium-WebView-95-ARM
# Android System WebView 95.0.4608.0 (ARM/armeabi)

本项目提供一个从 Chromium 官方源码编译的 `Android System WebView` 安装包，专门针对 **ARM/armeabi (ARMv5TE)** 架构，并兼容 **Android 5.0 (API Level 21)** 及以上系统。

## 关键信息
- **版本**：Chrome 95.0.4608.0
- **编译来源**：[Chromium 官方源码](https://chromium.googlesource.com/chromium/src/+/main/docs/android_build_instructions.md)
- **最低兼容**：Android 5.0 (API 21)
- **支持架构**：ARM/armeabi (ARMv5TE)
- **签名状态**：V1 + V2

## 适用场景
- 运行 Android 5.0+ 的老旧 ARMv5 设备
- 点读笔、学习机等嵌入式设备
- 需要标准 WebView 支持的定制化安卓设备

## 使用方法
1.  下载 `AndroidSystemWebView.armeabi.apk` 文件
2.  通过 ADB 或文件管理器安装：
    ```bash
    adb install AndroidSystemWebView.armeabi.apk
    ```

## 编译说明
本安装包严格遵循 Chromium 官方 [Android Build Instructions](https://chromium.googlesource.com/chromium/src/+/main/docs/android_build_instructions.md) 编译，仅指定 `target_cpu="arm"` 和 `android_api_level=21` 进行架构和 API 适配，未对源码进行任何额外修改。
