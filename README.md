Tandy XT-CF-Lite LAN Rev 0.9a ReadMe
----------------------------
This is a Compact Flash HD and Realtek LAN card for the Tandy 1400. It uses the expansion slot on the rear of the Tandy to add a bootable HD. 
The Realtek 8019AS is an NE2000 compatible. Uses the XT NE2000 packet driver. 

https://www.vcfed.org/forum/forum/genres/pcs-and-clones/41507-ne2000-packet-drivers-for-8-bit-slots


RSET8019.EXE for DOS, can set EEPROM parameters, also includes diagnostic functions

8-bit TANDY (ISA) CompactFlash interface + Boot ROM + LAN

Documentation for the switches can be found on the rear silkscreen. More ROM I/O addresses are possible than the information on the silkscreen. See below.

Credit:
-------
Design uses schematic from Sergey Kiselev, with a few small changes to switches, and PCB from scratch.\
www.malinov.com/Home/sergeys-projects/xt-cf-lite


https://www.lo-tech.co.uk/xt-cf-card-for-tandy-1400-series-laptops/
James Pearce for showing that this was possible a long long time ago.

XT-IDE Universal BIOS\
www.xtideuniversalbios.org  
www.xtideuniversalbios.org/binaries  
Use the latest working binary that includes XTIDECFG.COM (config utility), ide_xt.bin (8086/8088), ide_xtp.bin (80186/V20/V30 and up).




Further documentation:
----------------------

SW1 - ON: ROM Enabled; OFF: ROM Disabled\
SW2 - ON: EEPROM Write Enabled; OFF: EEPROM Write Disabled

---

SW3 - ROM I/O Port:  
123 ROM  
111 C0000  < Tandy Default  
110 C4000  
101 C8000  
101 CA000  
100 CC000  
011 D0000 
010 D4000  
001 D8000  
000 DC000  

Make sure that selected I/O and EEPROM addresses do not conflict with other devices.
Addresses 0xC0000 - 0xC6000 will conflict with EGA/VGA BIOS extension.
Addresses 0xC8000 - 0xCA000 might conflict with XT Hard Disk BIOS extension.
Addresses 0xE0000 and up might conflict with system BIOS on newer motherboards.
It is recommended to disable EEPROM write once XT IDE BIOS extension is programmed and configured.

---

SW4 - IDE I/O Port:  
123 IDE  
111 300 < Default  
011 320  
101 340  
001 360  
110 380  
010 3A0  
100 3C0  
000 3E0  

---

LAN 
Realtek 8019AS 93LC46 EEPROM
Due to height restrictions in the Tandy expansion bay, dont use an IC socket for the U7 93CXX   (93LC46)



---

| References | Value | Footprint | Quantity Per PCB |
|---|---|---|---|
| C1 C2 C3 C4 C5 C6 C15 C16 C17 C18 C19 | 100nF | C_0805_HandSoldering | 11 |
| C20 | 100nF | C_0805_HandSoldering | 1 |
| C7 C8 | 10uF | C_0805_HandSoldering | 2 |
| C21 | 47uF 10V | CP_Tantalum_Case-D_EIA-7343-31_Hand | 1 |
| C9 C10 C11 C12 C13 C14 | C | C_0805_HandSoldering | 6 |
| D1 | IDE LED | LED_D3.0mm | 1 |
| J2 | RJ45_LED_Shielded | 8P8C_yellow_green_Ckmtw_C133529 | 1 |
| J1 | Tandy_PCBEdgeBus_02x30 | Connector_PCBEdge_Tandy1400LT | 1 |
| P1 | CF_CARD | CF_Slot_3M_N7E50-7516TS0884 | 1 |
| P2 | IDE LED | PinHeader_1x02_P2.54mm_Horizontal | 1 |
| R3 | 200R | R_0805_HandSoldering | 1 |
| R5 R6 | 1K | R_0805_HandSoldering | 2 |
| R1 | 5.6k | C_0805_2012Metric_Pad1.15x1.40mm_HandSolder | 1 |
| R2 | 10K | C_0805_2012Metric_Pad1.15x1.40mm_HandSolder | 1 |
| R7 | 10K | R_0805_HandSoldering | 1 |
| R4 | 27k | R_0805_HandSoldering | 1 |
| RN1 RN2 RN3 | 10K | R_Array_Convex_4x1206 | 3 |
| RN4 | 1K | R_Array_Convex_4x1206 | 1 |
| SW4 | IDE Addr | SW_DIP_SPSTx03_Slide_9.78x9.8mm_W7.62mm_P2.54mm | 1 |
| SW3 | ROM Addr | SW_DIP_SPSTx03_Slide_9.78x9.8mm_W7.62mm_P2.54mm | 1 |
| SW1 | ROM Enable | CKCOMP-OS102011MA1QN1 | 1 |
| SW2 | ROM Write Enable | CKCOMP-OS102011MA1QN1 | 1 |
| T1 | 13F-39MNL | SOIC-16W-12_7.5x10.3mm_P1.27mm | 1 |
| U1 | 28C64 | DIP-28_W15.24mm_Socket | 1 |
| U5 | 74LS04 | SOIC-14_3.9x8.7mm_P1.27mm | 1 |
| U4 | 74LS32 | SOIC-14_3.9x8.7mm_P1.27mm | 1 |
| U2 U3 | 74LS688 | SOIC-20W_7.5x12.8mm_P1.27mm | 2 |
| U7 | 93CxxA | IC_DIP8_300 | 1 |
| U6 | RTL8019AS | LQFP-14x20mm_P0.5mmRealtek | 1 |
| Y2 | 20Mhz Crystal | Resonator-2pin_w8.0mm_h3.5mm | 1 |
