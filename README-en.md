**`Enlish`** | [简体中文](README.md)

[![Build](https://img.shields.io/badge/GitHub%20Actions-Build-181717?logo=github&logoColor=white&style=flat-square)](https://github.com/Numbersf/Action-Build/actions/workflows/Build%20SukiSU%20Ultra%20OnePlus.yml) [![Channel](https://img.shields.io/badge/Follow-Telegram-blue.svg?logo=telegram)](https://t.me/taichi91) [![OnePlus Kernel Manifest](https://img.shields.io/badge/OnePlus%20Kernel%20Manifest-EB0029?logo=oneplus&logoColor=white&style=flat-square)](https://github.com/OnePlusOSS/kernel_manifest)

# Action-Build
**```Build OnePlus SukiSU Ultra KPM Kernel```**

# Announcement

The ``_x`` suffix in the configuration file is the code name for the system version you are using. For example, ``_w Android16``, ``_v Android15``, ``_u Android14``, ``_t Android13``, ``_sAndroid12``, and so on—**in reverse alphabetical order, lowercase**. The one without a suffix is generally the factory ``Android`` version of a device model. Currently, I have only added devices with ``Android15``, that is, the ``_v`` suffix, in the pre-selection. If you are using another Android version, please manually change ``_v`` to another code name.

------

Regarding how long it takes to run, it is divided into four levels. Generally, the earlier the device model, the faster it runs.
>***Examples of time required for some models***
>>>1.sm8450, sm8475, sm8550

>>`30~35min,max:45min`
>>>2.sm7675, sm7550, sm8650

>>`1h1min~1h12min,max:1h32min`
>>>3.sm8750

>>`2h1min~2h22min,max:2h45min`
>>>4.Known special models: some non-A15 models

>>`1h22min~1h28min,max:?`
>
That is to say, if the running time for your device exceeds the maximum time above, please try to rerun and check ``step`` to ensure it is not an official issue.

------

Some devices have problems with ``lz4kd``, which are being fixed. **If it cannot run, please do not enable ``ZRAM algorithm`` for now**; please back up ``boot.img`` in advance.

------

Remember to **hold volume down** to install the module.

------
 
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
-- KPM is disabled by default.  
-- New `dir4` and `dir5` paths added to support `sm8750` and some devices with new paths when ZRAM is enabled (such as `ace2p`, `13T`).   [@ShirkNeko](https://github.com/ShirkNeko)  
-- Added support for the `LZ4K` compression algorithm in the `zram` module.   [@ShirkNeko](https://github.com/ShirkNeko)  
-- Synchronized changes with the upstream download channel for the `susfs` module to fix download issues.  
-- Optimized the build scheme for `sm8750` and `sm7675`.  
-- Fixed the version number error.  
-- New `dir3` path added to support `sm8475` (such as `ace2`).  
-- Supports automatic download of the latest `CI/Release` `susfs` module and uses `ksud` for installation.  
-- Supports `KPM` (copy without modifications) and `VFS HOOK` (optional).  