**简体中文** | [English](README-en.md)
 
[![Build](https://img.shields.io/badge/GitHub%20Actions-Build-181717?logo=github&logoColor=white&style=flat-square)](https://github.com/Numbersf/Action-Build/actions/workflows/Build%20SukiSU%20Ultra%20OnePlus.yml) [![Channel](https://img.shields.io/badge/Follow-Telegram-blue.svg?logo=telegram)](https://t.me/taichi91) [![OnePlus Kernel Manifest](https://img.shields.io/badge/OnePlus%20Kernel%20Manifest-EB0029?logo=oneplus&logoColor=white&style=flat-square)](https://github.com/OnePlusOSS/kernel_manifest)
 
# Action-Build
**```Build OnePlus SukiSU Ultra KPM Kernel```**
 
# 公告
 
配置文件中的``_x``后缀是你正在使用系统版本。``_v``是``Android15``、``_u``是``Android14``、``_t``是``Android13``、无后缀一般是一个机型出厂``Android``版本。
 
部分设备的``lz4kd``存在问题,修复中,**跑不出来请先不要启用``ZRAM算法``**
 
记得**音量下**安装模块
 
# 更新日志:
- 支持在``ak3.zip``中标明使用源码对应的``Android``版本号,例如:
```
AnyKernel3_SukiSUUltra_12866_oneplus_ace2pro_Android15_KPM_VFS.zip
```
- 新增```dir4、dir5```路径用于支持```sm8750和部分机型开启zram后的新路径```(比如```ace2p、13T```)
- 添加```zram```模块的```LZ4K```压缩算法支持
- 移除配置文件后缀可能存在的```_v```或者```_u```
- 同步```susfs```模块上游下载频道的变化,解决无法下载的问题
- 优化```sm8750、sm7675```的```build```方案
- 修复版本号错误
- 新增```dir3```路径用于支持```sm8475```(比如```ace2```)
- 支持自动下载最新```CI/Release```的```susfs```模块并调用```ksud```安装
- 支持```KPM```(无需任何修改复制什么的）、```VFS HOOK```（自选是否开启）