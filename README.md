# Compaq SLT/286 Memory Module

<img src="https://github.com/BeniD82/Compaq-SLT286-RAM/blob/BeniD82-patch-1/Images/module_3d.PNG" width="75%"> 

## Introduction

The Compaq SLT/286 laptop provides 640k of RAM in its stock configuration. The SLT/286 requires the use of proprietary PSRAM memory modules to expand available RAM which are unobtainable today. The intent of this project is to provide an economic, low-cost alternative to SLT/286 users, allowing them to upgrade their vintage system using 1MB SRAM modules instead.

Schematics for the custom module as well a set of Gerber files (based on the requirements of JLCPCB as well as PCBWAY) are porvided in this project.



## Bill of Materials

| Location | Part | Size / Case Code | Part number |
| --- | --- | --- | --- |
| IC1 | 1 Mbit SRAM (128K x 8), used for parity | SOP-32 | ASC6C1008-55SINTR |
| IC2 | 8 Mbit SRAM (1M x 16)  | TSOP-II | AS6C8016-55ZIN |
| C1, C2, C3 | 0.1uf MLCC capacitor | 1206 | Kyrocera/AVX 1206YC104JAT2A |




## Version History:

*   v0.3 (current)    
    \- Converted to a 4-layer design, using proper ground and power planes
*   v0.2   
    \- Reworked edge connector  
    \- Resized module dimensions
*   v0.1    
    \- Initial release



## Caveats

My tested systems encountered stability issues with three memory modules installed; it ran stable if only two memory modules had been installed in slot A (J116) and slot B (J117). If adding a third module to slot C (J118), or only populating slot C, the system became unstable, randomly generating “Parity Check 2 ?????” in DOS, and when using Windows 3.1, the system would freeze shortly after loading.

I was also able to reproduce the behavior if using one of the new modules in e.g. slot A and original PSRAM modules in slots B and C. I am uncertain if this behavior is related to the new memory modules, my systems, or a general issue with the hardware across the board.




## What about larger modules?

While the system can support up to 12.6 MB of RAM total, which requires the use of three 4MB modules, 1MB modules should be more than adequate, providing ample amounts of system memory, and in addition, will allow users to run Windows 3.1 on these machines, if they so choose. Creating larger modules would require significantly more expensive SRAM chips as well additional logic for address decoding, which I'm not certain would be worth the additional effort and expenditures.
