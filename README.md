Tandy XT-CF-Lite LAN Rev 0.9a ReadMe
----------------------------

8-bit TANDY (ISA) CompactFlash interface + Boot ROM + LAN

Documentation for the switches can be found on the rear silkscreen. More ROM I/O addresses are possible than the information on the silkscreen. See below.

Credit:
-------
Design uses schematic from Sergey Kiselev, with a few small changes to switches, and PCB from scratch.\
www.malinov.com/Home/sergeys-projects/xt-cf-lite

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



\begin{table}
\renewcommand{\arraystretch}{1.2}
\centering
\begin{tabular}{@{}lllll@{}}
\toprule
Part & References & Value & Footprint & Quantity Per PCB \\\midrule
C-xt-cf-rescue & C1 C2 C3 C4 C5 C6 C15 C16 C17 C18 C19 & 100nF & C\textunderscore0805\textunderscoreHandSoldering & \multicolumn{1}{|r|}{11} \\
C & C20 & 100nF & C\textunderscore0805\textunderscoreHandSoldering & \multicolumn{1}{|r|}{1} \\
CP1-xt-cf-rescue & C7 C8 & 10uF & C\textunderscore0805\textunderscoreHandSoldering & \multicolumn{1}{|r|}{2} \\
C & C21 & 47uF 10V & CP\textunderscoreTantalum\textunderscoreCase-D\textunderscoreEIA-7343-31\textunderscoreHand & \multicolumn{1}{|r|}{1} \\
C & C9 C10 C11 C12 C13 C14 & C & C\textunderscore0805\textunderscoreHandSoldering & \multicolumn{1}{|r|}{6} \\
LED & D1 & IDE LED & LED\textunderscoreD3.0mm & \multicolumn{1}{|r|}{1} \\
RJ45\textunderscoreLED\textunderscoreShielded & J2 & RJ45\textunderscoreLED\textunderscoreShielded & 8P8C\textunderscoreyellow\textunderscoregreen\textunderscoreCkmtw\textunderscoreC133529 & \multicolumn{1}{|r|}{1} \\
Tandy\textunderscorePCBEdgeBus\textunderscore02x30 & J1 & Tandy\textunderscorePCBEdgeBus\textunderscore02x30 & Connector\textunderscorePCBEdge\textunderscoreTandy1400LT & \multicolumn{1}{|r|}{1} \\
CF\textunderscoreCARD-xt-cf-rescue & P1 & CF\textunderscoreCARD & CF\textunderscoreSlot\textunderscore3M\textunderscoreN7E50-7516TS0884 & \multicolumn{1}{|r|}{1} \\
CONN\textunderscore2-xt-cf-rescue & P2 & IDE LED & PinHeader\textunderscore1x02\textunderscoreP2.54mm\textunderscoreHorizontal & \multicolumn{1}{|r|}{1} \\
R & R3 & 200R & R\textunderscore0805\textunderscoreHandSoldering & \multicolumn{1}{|r|}{1} \\
R & R5 R6 & 1K & R\textunderscore0805\textunderscoreHandSoldering & \multicolumn{1}{|r|}{2} \\
R-xt-cf-rescue & R1 & 5.6k & C\textunderscore0805\textunderscore2012Metric\textunderscorePad1.15x1.40mm\textunderscoreHandSolder & \multicolumn{1}{|r|}{1} \\
R-xt-cf-rescue & R2 & 10K & C\textunderscore0805\textunderscore2012Metric\textunderscorePad1.15x1.40mm\textunderscoreHandSolder & \multicolumn{1}{|r|}{1} \\
R & R7 & 10K & R\textunderscore0805\textunderscoreHandSoldering & \multicolumn{1}{|r|}{1} \\
R & R4 & 27k & R\textunderscore0805\textunderscoreHandSoldering & \multicolumn{1}{|r|}{1} \\
R\textunderscorePack04 & RN1 RN2 RN3 & 10K & R\textunderscoreArray\textunderscoreConvex\textunderscore4x1206 & \multicolumn{1}{|r|}{3} \\
R\textunderscorePack04 & RN4 & 1K & R\textunderscoreArray\textunderscoreConvex\textunderscore4x1206 & \multicolumn{1}{|r|}{1} \\
SW\textunderscoreDIP\textunderscorex03 & SW4 & IDE Addr & SW\textunderscoreDIP\textunderscoreSPSTx03\textunderscoreSlide\textunderscore9.78x9.8mm\textunderscoreW7.62mm\textunderscoreP2.54mm & \multicolumn{1}{|r|}{1} \\
SW\textunderscoreDIP\textunderscorex03 & SW3 & ROM Addr & SW\textunderscoreDIP\textunderscoreSPSTx03\textunderscoreSlide\textunderscore9.78x9.8mm\textunderscoreW7.62mm\textunderscoreP2.54mm & \multicolumn{1}{|r|}{1} \\
SW\textunderscoreSPDT & SW1 & ROM Enable & CKCOMP-OS102011MA1QN1 & \multicolumn{1}{|r|}{1} \\
SW\textunderscoreSPDT & SW2 & ROM Write Enable & CKCOMP-OS102011MA1QN1 & \multicolumn{1}{|r|}{1} \\
13F-39MNL & T1 & 13F-39MNL & SOIC-16W-12\textunderscore7.5x10.3mm\textunderscoreP1.27mm & \multicolumn{1}{|r|}{1} \\
28C64-xt-cf-rescue & U1 & 28C64 & DIP-28\textunderscoreW15.24mm\textunderscoreSocket & \multicolumn{1}{|r|}{1} \\
74LS04-xt-cf-rescue & U5 & 74LS04 & SOIC-14\textunderscore3.9x8.7mm\textunderscoreP1.27mm & \multicolumn{1}{|r|}{1} \\
74LS32-xt-cf-rescue & U4 & 74LS32 & SOIC-14\textunderscore3.9x8.7mm\textunderscoreP1.27mm & \multicolumn{1}{|r|}{1} \\
74LS688-xt-cf-rescue & U2 U3 & 74LS688 & SOIC-20W\textunderscore7.5x12.8mm\textunderscoreP1.27mm & \multicolumn{1}{|r|}{2} \\
93CxxA & U7 & 93CxxA & IC\textunderscoreDIP8\textunderscore300 & \multicolumn{1}{|r|}{1} \\
RTL8019AS & U6 & RTL8019AS & LQFP-14x20mm\textunderscoreP0.5mmRealtek & \multicolumn{1}{|r|}{1} \\
Crystal & Y2 & 20Mhz Crystal & Resonator-2pin\textunderscorew8.0mm\textunderscoreh3.5mm & \multicolumn{1}{|r|}{1} \\\bottomrule

\end{tabular}
\caption{xt-cf-tandy_bom_1.01}
\end{table}
