**Enlish** | [简体中文](README.md)
 
[![Build](https://img.shields.io/badge/GitHub%20Actions-Build-181717?logo=github&logoColor=white&style=flat-square)](https://github.com/Numbersf/Action-Build/actions/workflows/Build%20SukiSU%20Ultra%20OnePlus.yml) [![Channel](https://img.shields.io/badge/Follow-Telegram-blue.svg?logo=telegram)](https://t.me/taichi91) [![OnePlus Kernel Manifest](https://img.shields.io/badge/OnePlus%20Kernel%20Manifest-EB0029?logo=oneplus&logoColor=white&style=flat-square)](https://github.com/OnePlusOSS/kernel_manifest)
 
# Action-Build  
**```Build OnePlus SukiSU Ultra KPM Kernel```**
 
# Announcement  
The _x suffix in the configuration file indicates the system version you are currently using. _v stands for Android 15, _u for Android 14, _t for Android 13, and no suffix usually refers to the factory Android version of the device model.
 
Some devices have issues with ``lz4kd``, currently under investigation. **If it fails to boot, please do not enable ``ZRAM``**
 
Remember to install the module with **Volume Down**
 
# Changelog:  
- Support specifying the corresponding source `Android` version in `ak3.zip`, for example:
```
AnyKernel3_SukiSUUltra_12866_oneplus_ace2pro_Android15_KPM_VFS.zip
```
- Added ```dir4``` and ```dir5``` paths to support ```sm8750 and some models with zram enabled``` (e.g. ```ace2p```, ```13T```)
- Added support for the ```LZ4K``` compression algorithm in the ```zram``` module
- Removed possible ```_v``` or ```_u``` suffixes from configuration files
- Synced changes of the ```susfs``` module's upstream download channel to fix the download issue
- Optimized the ```build``` scheme for ```sm8750``` and ```sm7675```
- Fixed incorrect version number
- Added ```dir3``` path to support ```sm8475``` (e.g. ```ace2```)
- Supported automatic download of the latest ```CI/Release``` ```susfs``` module and installation via ```ksud```
- Supported ```KPM``` (no need to copy or modify anything), and ```VFS HOOK``` (optional to enable)