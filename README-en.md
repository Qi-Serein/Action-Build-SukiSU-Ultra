**`Enlish`** | [简体中文](README.md)

[![Build](https://img.shields.io/badge/GitHub%20Actions-Build-181717?logo=github&logoColor=white&style=flat-square)](https://github.com/Numbersf/Action-Build/actions/workflows/Build%20SukiSU%20Ultra%20OnePlus.yml) [![Channel](https://img.shields.io/badge/Follow-Telegram-blue.svg?logo=telegram)](https://t.me/taichi91) [![OnePlus Kernel Manifest](https://img.shields.io/badge/OnePlus%20Kernel%20Manifest-EB0029?logo=oneplus&logoColor=white&style=flat-square)](https://github.com/OnePlusOSS/kernel_manifest)

# Action-Build
**```Build OnePlus SukiSU Ultra KPM Kernel```**

# Announcement

The _x suffix in the configuration file indicates the codename of the Android version you are currently using. For example, `_w corresponds to Android 16, _v to Android 15, _u to Android 14, _t to Android 13, and _s to Android 12.` A configuration without any suffix usually refers to the device's factory Android version.
 
Some devices have issues with `lz4kd`, and a fix is in progress. **If the build fails, please do NOT enable the `ZRAM algorithm`**, and make sure to back up your `boot.img` in advance!
 
Special handling is required for `OnePlus Ace5Pro (ColorOS)` and `OnePlus 13 (ColorOS)`, and you must replace the `dtbo.img`.
 
Remember to install the module with **volume down**.
 
# Changelog
-- Remove potential version code from the suffix of the configuration file written to `ak3.zip` and replace it with the exact `Android` version number `XX.X.X`.  
```
Examples:
AnyKernel3_SukiSUUltra_12896_oneplus_ace2pro_Android15.0.0_KPM_VFS.zip  
AnyKernel3_SukiSUUltra_12896_oneplus_13_Android15.0.2_KPM_VFS.zip  
AnyKernel3_SukiSUUltra_12896_oneplus_11_Android14.1.0_KPM_VFS.zip
```  
-- Temporarily fixed the build issue for `OnePlus Ace5Pro` and `OnePlus 13` [@reigadegr](https://github.com/reigadegr)  
-- Allow custom kernel suffix  <- **`beta`**
```
1. When the custom kernel suffix is empty, a random string is used instead of the default “x.xx.xxx-androidxx-8-o-g3b1e97b8b29f”
 
2. When custom suffix is enabled, the kernel version is modified to “x.xx.xxx-androidxx-[custom content]”, and the original “androidxx-8-o-g3b1e97b8b29f” is no longer retained.
```  
-- KPM is disabled by default By Qi_Serein
-- New `dir4` and `dir5` paths added to support `sm8750` and some devices with new paths when ZRAM is enabled (such as `ace2p`, `13T`).   [@ShirkNeko](https://github.com/ShirkNeko)  
-- Added support for the `LZ4K` compression algorithm in the `zram` module.   [@ShirkNeko](https://github.com/ShirkNeko)  
-- Synchronized changes with the upstream download channel for the `susfs` module to fix download issues.  
-- Optimized the build scheme for `sm8750` and `sm7675`.  
-- Fixed the version number error.  
-- New `dir3` path added to support `sm8475` (such as `ace2`).  
-- Supports automatic download of the latest `CI/Release` `susfs` module and uses `ksud` for installation.  
-- Supports `KPM` (copy without modifications) and `VFS HOOK` (optional).  
