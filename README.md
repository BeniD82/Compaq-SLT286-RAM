# Compaq SLT/286 Memory Module

<img src="https://github.com/BeniD82/Compaq-SLT286-RAM/blob/main/Images/module_3d.PNG" width="75%"> 



## Introduction

The Compaq SLT/286 laptop provides 640k of RAM in its stock configuration. The SLT/286 requires the use of proprietary PSRAM memory modules to expand available RAM which are unobtainable today. The intent of this project is to provide an economic, low-cost alternative to SLT/286 users, allowing them to upgrade their vintage system using 1MB SRAM modules instead.

Schematics for the custom module as well Gerber files for PCB manufacturing are porvided in this project.



## Bill of Materials

| Location | Part | Package / Case Code | Part number |
| --- | --- | --- | --- |
| IC1 | 1 Mbit SRAM (128K x 8), used for parity | SOP-32 | AS6C1008-55SINTR |
| IC2 | 8 Mbit SRAM (512K x 16)  | TSOP-II | AS6C8016-55ZIN |
| C1, C2, C3 | 0.1uf MLCC capacitor | 1206 | Kyrocera/AVX 1206YC104JAT2A |

## PCB Manufacturing and Assembly

The Gerber files necessary for manufacturing the PCB were generated based on the parameters provided by JLCPCB as well as PCBWay. The board is a four layer board (layers top to bottom: F.Cu, In1.Cu, In2.Cu, B.Cu). I would recommend ENIG plating as I feel that it does makes soldering the 8 Mbit TSOP chip somewhat easier as the pins have a rather fine pitch, but this will increse the overall time and cost of manufacturing. Also, it might be advisable to have a chamfer added to the edge connector, though not all manufacturing houses will be able to do that based on the small size of the board. This would also incur additional cost. Without chamfer the modules can still be inserted without an issue, just be careful and don't brute force insertion (take your time). It will be a tight fit, just like with the original modules. 

## Caveats

I own two SLT/286 systems, and on both I encountered stability issues if I had three memory modules installed; it runs stable with two modules, one in slot A (J116) and the other slot B (J117). If adding a third module to slot C (J118 - closest to the board edge), or if only populating slot C, the system became unstable, randomly generating “Parity Check 2 ?????” errors in DOS, and when using Windows 3.1, the system would freeze shortly after loading.

I was also able to reproduce the behavior if using one of the new modules in slot A and adding the original PSRAM modules to slots B and C. I am uncertain if this behavior is related to the new memory modules, my systems, or a general issue with the SLT/286 series itself. I also tested by adding a bulk capacitor to the power pins on the RAM card but the behavior remained the same. Therefore, your mileage may vary.



## What about larger modules?

While the system can support up to 12.6 MB of RAM total, which requires the use of three 4MB modules, I feel that 1MB modules are more than sufficient for a 286 based system, considering most software will not require more than a couple of megs at most, and Windows 3.1 will run fine with 2-3MB on the SLT/286. Creating larger modules would require significantly more expensive SRAM chips as well additional logic for address decoding, which I'm not certain would be worth the additional effort and expenditure.



## Image Gallery

| ![](https://github.com/BeniD82/Compaq-SLT286-RAM/blob/main/Images/3MB_installed.jpg) | ![](https://github.com/BeniD82/Compaq-SLT286-RAM/blob/main/Images/test_checkit3.jpg) |
| :---------------: | :---------------: |
| ![](https://github.com/BeniD82/Compaq-SLT286-RAM/blob/main/Images/boot_mem.jpg) | ![](https://github.com/BeniD82/Compaq-SLT286-RAM/blob/main/Images/test_winsleuth3.jpg) |

## Version History:

*   v0.3 (current)    
    + Converted board to a 4-layer design, using proper ground and power planes
*   v0.2   
    + Revised edge connector
    + Revised module dimensions
    + Removed footprint for bulk capacitor (SRAM power draw is miniscule; did not feel it's necessary to keep it)
*   v0.1    
    + Initial release
