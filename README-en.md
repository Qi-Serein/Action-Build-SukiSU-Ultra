**`Enlish`** | [简体中文](README.md)

[![Build](https://img.shields.io/badge/GitHub%20Actions-Build-181717?logo=github&logoColor=white&style=flat-square)](https://github.com/Numbersf/Action-Build/actions/workflows/Build%20SukiSU%20Ultra%20OnePlus.yml) [![Channel](https://img.shields.io/badge/Follow-Telegram-blue.svg?logo=telegram)](https://t.me/taichi91) [![OnePlus Kernel Manifest](https://img.shields.io/badge/OnePlus%20Kernel%20Manifest-EB0029?logo=oneplus&logoColor=white&style=flat-square)](https://github.com/OnePlusOSS/kernel_manifest) [![Coolapk](https://img.shields.io/badge/Follow-Coolapk-3DDC84?style=flat-square&logo=android&logoColor=white)](http://www.coolapk.com/u/28259173) [![Coolapk](https://img.shields.io/badge/Follow-Coolapk-3DDC84?style=flat-square&logo=android&logoColor=white)](http://www.coolapk.com/u/23244807)
 

# Action-Build
**```Build OnePlus SukiSU Ultra KPM Kernel```**
<details>
<summary><strong>Click to view how to fork</strong></summary>
<img src="https://github.com/Numbersf/Action-Build/blob/main/pic%2Fmake.gif" width="500"/>
</details>
<details>
<summary><strong>Click to view how to synchronize the forked project to the latest</strong></summary>
<img src="https://github.com/Numbersf/Action-Build/blob/main/pic%2Fsyncfork.png" width="150"/>
<summary>Please sync in time! Some updates may cause old versions to become invalid!</summary>
</details>

# Announcements

------
> [!NOTE]  
> The `_x` suffix in the config file corresponds to the code name of your current Android system version. The codes are in reverse alphabetical order and lowercase. A config without any suffix usually refers to the device’s stock Android version. Currently, only Android 15 (`_v`) variants are preset. If you are using a different version, please manually replace `_v` with the appropriate code.
> <details>
> <summary><strong>Click to view the Android version codes (subject to future updates)</strong></summary>
>
>`_z Android19 (Zebra Cake)`
>
>`_y Android18 (Yogurt Parfait)`
>
>`_x Android17 (Xmas Pudding)`
>
>`_w Android16 (Wedding Cake)`<strong>
>
>`_v Android15 (Vanilla Ice Cream)`
>
>`_u Android14 (Upside Down Cake)`
>
>`_t Android13 (Tiramisu)`
>
>`_s Android12 (Snow Cone)`</strong>
>
>`_r Android11 (Red Velvet Cake)`
>
>`_q Android10 (Quince Tart)`
>
>`_p Android9 (Pie)`
>
>`_o Android8 (Oreo)`
>
>`_n Android7 (Nougat)`
>
>`_m Android6 (Marshmallow)`
>
>`_l Android5 (Lollipop)`
>
>`_k Android4.4 (KitKat)`
>
>`_j Android4.3–4.1 (Jelly Bean)`
>
>`_i Android4.0 (Ice Cream Sandwich)`
>
>`_h Android3.x (Honeycomb)`
>
>`_g Android2.3 (Gingerbread)`
>
>`_f Android2.2 (FroYo)`
>
>`_e Android2.1 (Eclair)`
>
>`_d Android1.6 (Donut)`
>
>`_c Android1.5 (Cupcake)`
>
> </details>

------
> [!IMPORTANT]  
> About compile time: generally, older devices build faster.  
> <details>
> <summary><strong>Click to view compile time Using Fast Build (clang make)</strong></summary>
>
>>>>0.Known exceptions: some non-A15 models (e.g. OnePlus 11-A14;OnePlus 11-A13)
>
>>>`1h8min~1h17min,max:1h17min`
>>>>0.All Other Devices
> 
>>>`22min~31min,max:35min`
> 
> </details>
> <details>
> <summary><strong>Click to view compile time Using official build.sh</strong></summary>
>
>>>>0.Known exceptions: some non-A15 models (e.g. OnePlus 11-A14;OnePlus 11-A13)
> 
>>>`1h14min~1h28min,max:1h28min`
>>>>1.sm8450, sm8475, sm8550
> 
>>>`30~35min,max:45min`
>>>>2.sm7675, sm7550, sm8650
> 
>>>`1h1min~1h12min,max:1h32min`
>>>>3.sm8750
> 
>>>`2h1min~2h22min,max:2h45min`
>> 
> </details>
>
> So, if your runtime exceeds the max time listed, try rerunning and check the `step` logs in case it's a platform issue.

------
> [!WARNING]  
> Some devices have issues with `lz4kd`. Fix in progress. **If the build fails, please do not enable `ZRAM` compression**, and back up your `boot.img` in advance.

------
> [!CAUTION]  
> **Do not install modules when performing a root-preserving update!**

> [!TIP]  
> Remember to press **Volume Down** when installing modules!

 
------
 
# Changelog
--Fix the problem that the official script cannot run when the kernel version is between `5.15.0-5.15.123`, and the result of the quick compilation has problems. [@zzh20188](https://github.com/zzh20188)  
--Support `BBR`, not enabled by default.  
-- Allow custom kernel suffix.  <- **`beta`**
```
1. When the custom kernel suffix is empty, a random string is used instead of the default “x.xx.xxx-androidxx-8-o-g3b1e97b8b29f”
2. When custom suffix is enabled, the kernel version is modified to “x.xx.xxx-androidxx-[custom content]”, and the original “androidxx-8-o-g3b1e97b8b29f” is no longer retained.
3. When using clang make (Fast Build), add the missing kernel android version number to the new source kernel information x.xx.xxx-o-g3b1e97b8b29f, and then perform operations in 1 or 2.
```  
-- Support ultra-fast builds for some models `(currently supports 5.10, 5.15, 6.1, 6.6)`  
-- Fixed OnePlus Ace5Pro and OnePlus 13 boot issues after build failure; using official dtbo now allows booting directly. [@reigadegr](https://github.com/reigadegr)  
-- Support displaying user-defined inputs during `Show selected inputs debug` step; workflow name will also reflect some values.  
-- Removed potential version codes from the suffix of `ak3.zip` config file, replaced with exact `Android` version numbers `XX.X.X`.
```
Examples:
AnyKernel3_SukiSUUltra_12896_oneplus_ace2pro_Android15.0.0_KPM_VFS.zip  
AnyKernel3_SukiSUUltra_12896_oneplus_13_Android15.0.2_KPM_VFS.zip  
AnyKernel3_SukiSUUltra_12896_oneplus_11_Android14.1.0_KPM_VFS.zip
```  
-- KPM is disabled by default.  
-- New `dir4` and `dir5` paths added to support `sm8750` and some devices with new paths when ZRAM is enabled (such as `ace2p`, `13T`).   [@ShirkNeko](https://github.com/ShirkNeko)  
-- Added support for the `LZ4K` compression algorithm in the `zram` module.   [@ShirkNeko](https://github.com/ShirkNeko)  
-- Synchronized changes with the upstream download channel for the `susfs` module to fix download issues.  
-- Optimized the build scheme for `sm8750` and `sm7675`.  
-- New `dir3` path added to support `sm8475` (such as `ace2`).  
-- Support automatic download of latest `CI` version of `susfs` module and install via `ksud`; also automatically extracts manager `CI-APK` but does not install it.  
-- Supports `VFS HOOK` (optional).  
