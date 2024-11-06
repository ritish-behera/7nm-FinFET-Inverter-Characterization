# Characterization of CMOS Inverter For ASAP 7nm FinFET Technology Through SPICE Simulations
The primary objective of this project was to characterize an inverter design using ASAP 7nm FinFET technology. The project involved performing SPICE simulations to analyze the performance of the inverter in terms of key metrics such as propagation delay, power consumption, noise margin, gain and switching characteristics.

<details>
  <summary>Click to expand!</summary>

  Here is the content that will be hidden until you click "expand."
  You can add text, code, lists, or any other markdown here.

  ```python
  # Example code block
  print("Hello, world!")
```
</details>

# Final Datasheet for CMOS Inverter in ASAP 7nm Technology

| nfin | pfin | Vth (V) | Gain (V) | NML (V) | NMH (V) | Id (uA) | Power    | Prop. Delay (ps) | Output Resistance (MOhm) | Frequency (THz) |
|------|------|---------|----------|---------|---------|---------|----------|------------------|--------------------------|-----------------|
|   14 |   14 |   0.344 |    6.425 |   0.176 |   0.194 |  226.56 | 2.37E-05 |           0.6086 |                 0.001518 |        0.821558 |
|   14 |   18 |   0.362 |    6.435 |   0.198 |   0.165 |  252.95 | 2.66E-05 |         0.913314 |                 0.001431 |        0.547457 |
|   14 |   10 |   0.321 |    6.473 |   0.133 |   0.235 |  192.98 | 2.00E-05 |         0.217335 |                 0.001663 |        2.300596 |
|   14 |   15 |    0.34 |     6.43 |   0.163 |   0.202 |     240 | 2.45E-05 |         0.691236 |                 0.001417 |        0.723342 |
|   15 |   13 |   0.334 |    6.435 |   0.154 |   0.211 |     226 | 2.36E-05 |         0.439567 |                 0.001478 |        1.137483 |
|   12 |   15 |    0.36 |    6.434 |   0.194 |    0.17 |     216 | 2.25E-05 |         0.878491 |                 0.001667 |        0.569158 |
|   13 |   14 |   0.349 |    6.425 |   0.177 |   0.187 |  219.31 | 2.28E-05 |         0.697454 |                 0.001591 |        0.716893 |
|   12 |   13 |    0.35 |    6.426 |   0.179 |   0.185 |  201.75 | 2.11E-05 |         0.704701 |                 0.001735 |        0.709521 |
|   11 |   12 |  0.3508 |     6.43 |   0.179 |   0.184 |   185.4 | 1.94E-05 |         0.713258 |                 0.001892 |        0.701009 |
|   15 |   16 |  0.3492 |    6.424 |   0.177 |   0.187 |  249.75 | 2.62E-05 |         0.685843 |                 0.001398 |         0.72903 |
|   15 |   15 |  0.3447 |    6.424 |   0.168 |   0.196 |     243 | 2.54E-05 |         0.608641 |                 0.001419 |        0.821502 |
|   13 |   15 |   0.354 |     6.43 |   0.186 |   0.179 |  224.16 | 2.35E-05 |         0.780879 |                 0.001579 |        0.640304 |
|   12 |   16 |   0.364 |     6.44 |   0.202 |   0.162 |   219.8 | 2.32E-05 |         0.957851 |                 0.001656 |        0.522002 |
|   11 |   13 |   0.356 |    6.426 |   0.188 |   0.175 |  191.93 | 2.01E-05 |         0.810269 |                 0.001855 |        0.617079 |

# Tools Used:
- ASAP 7nm PDK
- Ngspice for circuit simulations (SPICE)
- Xschem for schematic capture


# NGSPICE

Ngspice is a powerful open-source electronic circuit simulator, extending from the Berkeley SPICE3f5 core. It is widely used for simulating both analog and digital circuits. With its broad feature set, Ngspice can perform various types of analysis like DC, AC, transient, and noise, making it a versatile tool for engineers and researchers. It supports a wide range of device models, including diodes, MOSFETs, BJTs, and more.

Typical applications include analog circuit design, mixed-signal simulation, and educational use for teaching circuit principles. Ngspice is continuously maintained by a large community and is compatible with numerous SPICE models and netlists.

For comprehensive documentation, refer to the Ngspice manual.

## Installing Ngspice on Ubuntu 22.04
To install Ngspice, follow these steps in your terminal:
```
#Clone the Ngspice repository
git clone https://git.code.sf.net/p/ngspice/ngspice ngspice_git
cd ngspice_git
mkdir release
./autogen.sh
cd release
../configure --with-x --enable-xspice --disable-debug --enable-cider --with-readline=yes --enable-openmp --enable-osdi
make
sudo make install
```

# XSCHEM

Xschem is a graphical schematic capture tool designed for creating and simulating electronic circuit schematics. It allows users to design circuits visually and interfaces with various simulation tools, including SPICE simulators, to perform analysis and verification of circuit behavior.

## Installing Xschem on Ubuntu 22.04

To install Xschem on your Ubuntu 22.04 workstation, open your terminal and execute the following commands sequentially or copy them into a script for batch execution:
```
# Clone the Xschem repository
git clone https://github.com/StefanSchippers/xschem.git xschem
cd xschem
./configure
make
sudo make install
cd ..
```

# ASAP 7nm PDK

ASAP7nm is a process design kit (PDK) developed through collaboration between academia and industry, providing an advanced semiconductor technology node for integrated circuit (IC) design. This 7nm PDK is instrumental for researchers and engineers in designing high-performance, low-power chips with a high density of transistors. It is widely used for experimenting with nanoscale IC designs and for teaching semiconductor principles.

To install the ASAP7nm PDK, clone the repository using:
```
git clone https://github.com/The-OpenROAD-Project/asap7
```

# BSIM-CMG Model

BSIM-CMG (Berkeley Short-channel IGFET Model for Common Multi-Gate Structure) is a compact model designed for simulating FinFETs and other multi-gate transistor devices. It accounts for various advanced physical effects like quantum mechanics and short-channel effects, making it a critical tool for accurate simulation at nanoscale technologies.

For simulating FinFET devices, you can use the BSIM-CMG model. The .pm files are modified to .sp files for easier integration with the simulation setup. The model files are in Verilog-A format (extension .va) and can be compiled using the OpenVAF compiler, generating .osdi files required for Ngspice.

You can obtain the latest FinFET models from the BSIM-CMG website.

After compiling Verilog-A files to .osdi, place them in the same directory as your .sp file. Ensure that the latest Ngspice version, which supports .osdi files, is installed.

For more information on OpenVAF and compilation, visit OpenVAF documentation.

## Creating Symbols in Xschem

Xschem allows users to create custom symbols for devices if the PDK doesn’t provide them by default. As long as SPICE models are available, you can design symbols for transistors, diodes, resistors, and other components.

For example, to link a BSIM-CMG .osdi file to a symbol in Xschem, modify the .sym file by including the absolute path to the .osdi file:
```
.control
pre_osdi <ABSOLUTE_PATH_TO_OSDI_FILE>
.endc
```
By following these steps, you can fully integrate your SPICE models into Xschem and begin simulating your designs using the ASAP7nm PDK.

# Design and Simulation

After installing NGSPICE and XSCHEM and setting up the ASAP 7nm PDK, the characteristic simulation for the nfet and pfet can be performed followed by circuit design.

## 7nm PMOS and NMOS Characteristics

The generated SPICE deck for nmos and pmos characteristics from the XSCHEM schematic is as follows:

<details>
  <summary>NMOS SPICE Deck</summary>

```
** sch_path: /home/sudo-ritish/Desktop/asap_7nm_Xschem/nfet_char.sch
**.subckt nfet_char
V1 nfet_in GND 0
V2 vdd GND 3
R1 vdd nfet_out 1k m=1
Xnfet2 nfet_out nfet_in GND GND asap_7nm_nfet l=7e-009 nfin=12
**** begin user architecture code


.dc v1 0 0.7 1m v2 0 0.7 0.2
.control
run
set xbrushwidth=3
let vd = vdd - nfet_out
let id  = vd/1000
plot id
.endc


**** end user architecture code
**.ends
.GLOBAL GND
**** begin user architecture code

.subckt asap_7nm_nfet S G D B l=7e-009 nfin=14
	nnmos_finfet S G D B BSIMCMG_osdi_N l=7e-009 nfin=14
.ends asap_7nm_nfet

.model BSIMCMG_osdi_N BSIMCMG_va (
+ TYPE = 1
************************************************************
*                         general                          *
************************************************************
+version = 107             bulkmod = 1               igcmod  = 1               igbmod  = 0
+gidlmod = 1               iimod   = 0               geomod  = 1               rdsmod  = 0
+rgatemod= 0               rgeomod = 0               shmod   = 0               nqsmod  = 0
+coremod = 0               cgeomod = 0               capmod  = 0               tnom    = 25
+eot     = 1e-009          eotbox  = 1.4e-007        eotacc  = 1e-010          tfin    = 6.5e-009
+toxp    = 2.1e-009        nbody   = 1e+022          phig    = 4.2466          epsrox  = 3.9
+epsrsub = 11.9            easub   = 4.05            ni0sub  = 1.1e+016        bg0sub  = 1.17
+nc0sub  = 2.86e+025       nsd     = 2e+026          ngate   = 0               nseg    = 5
+l       = 2.1e-008        xl      = 1e-009          lint    = -2e-009         dlc     = 0
+dlbin   = 0               hfin    = 3.2e-008        deltaw  = 0               deltawcv= 0
+sdterm  = 0               epsrsp  = 3.9             nfin    = 1
+toxg    = 1.80e-009
************************************************************
*                            dc                            *
************************************************************
+cit     = 0               cdsc    = 0.01            cdscd   = 0.01            dvt0    = 1
+dvt1    = 0.47            phin    = 0.05            eta0    = 0.07            dsub    = 0.35
+k1rsce  = 0               lpe0    = 0               dvtshift= 0               qmfactor= 2.5
+etaqm   = 0.54            qm0     = 0.001           pqm     = 0.66            u0      = 0.0303
+etamob  = 2               up      = 0               ua      = 0.55            eu      = 1.2
+ud      = 0               ucs     = 1               rdswmin = 0               rdsw    = 200
+wr      = 1               rswmin  = 0               rdwmin  = 0               rshs    = 0
+rshd    = 0               vsat    = 70000           deltavsat= 0.2             ksativ  = 2
+mexp    = 4               ptwg    = 30              pclm    = 0.05            pclmg   = 0
+pdibl1  = 0               pdibl2  = 0.002           drout   = 1               pvag    = 0
+fpitch  = 2.7e-008        rth0    = 0.225           cth0    = 1.243e-006      wth0    = 2.6e-007
+lcdscd  = 5e-005          lcdscdr = 5e-005          lrdsw   = 0.2             lvsat   = 0
************************************************************
*                         leakage                          *
************************************************************
+aigc    = 0.014           bigc    = 0.005           cigc    = 0.25            dlcigs  = 1e-009
+dlcigd  = 1e-009          aigs    = 0.0115          aigd    = 0.0115          bigs    = 0.00332
+bigd    = 0.00332         cigs    = 0.35            cigd    = 0.35            poxedge = 1.1
+agidl   = 1e-012          agisl   = 1e-012          bgidl   = 10000000        bgisl   = 10000000
+egidl   = 0.35            egisl   = 0.35
************************************************************
*                            rf                            *
************************************************************
************************************************************
*                         junction                         *
************************************************************
************************************************************
*                       capacitance                        *
************************************************************
+cfs     = 0               cfd     = 0               cgso    = 1.6e-010        cgdo    = 1.6e-010
+cgsl    = 0               cgdl    = 0               ckappas = 0.6             ckappad = 0.6
+cgbo    = 0               cgbl    = 0
************************************************************
*                       temperature                        *
************************************************************
+tbgasub = 0.000473        tbgbsub = 636             kt1     = 0               kt1l    = 0
+ute     = -0.7            utl     = 0               ua1     = 0.001032        ud1     = 0
+ucste   = -0.004775       at      = 0.001           ptwgt   = 0.004           tmexp   = 0
+prt     = 0               tgidl   = -0.007          igt     = 2.5
************************************************************
*                          noise                           *
************************************************************
**)
.control
pre_osdi /home/sudo-ritish/Desktop/asap_7nm_Xschem/bsimcmg.osdi
.endc


**** end user architecture code
.end
```
</details>

<details>
  <summary>PMOS SPICE Deck</summary>
	
PMOS
```
** sch_path: /home/sudo-ritish/Desktop/asap_7nm_Xschem/pfet_char.sch
**.subckt pfet_char
V1 pfet_in GND 0
V2 vdd GND 3
R1 vdd pfet_out 1k m=1
Xpfet2 pfet_out pfet_in GND GND asap_7nm_pfet l=7e-009 nfin=14
**** begin user architecture code

.dc v1 -0.7 0 1m v2 -0.7 0 0.2
.control
run
set xbrushwidth=3
let vd = vdd - pfet_out
let id  = vd/1000
plot id
.endc


**** end user architecture code
**.ends
.GLOBAL GND
**** begin user architecture code

.subckt asap_7nm_pfet S G D B l=7e-009 nfin=14
	npmos_finfet S G D B BSIMCMG_osdi_P l=7e-009 nfin=14
.ends asap_7nm_pfet

.model BSIMCMG_osdi_P BSIMCMG_va (
+ TYPE = 0

************************************************************
*                         general                          *
************************************************************
+version = 107             bulkmod = 1               igcmod  = 1               igbmod  = 0
+gidlmod = 1               iimod   = 0               geomod  = 1               rdsmod  = 0
+rgatemod= 0               rgeomod = 0               shmod   = 0               nqsmod  = 0
+coremod = 0               cgeomod = 0               capmod  = 0               tnom    = 25
+eot     = 1e-009          eotbox  = 1.4e-007        eotacc  = 3e-010          tfin    = 6.5e-009
+toxp    = 2.1e-009        nbody   = 1e+022          phig    = 4.9278          epsrox  = 3.9
+epsrsub = 11.9            easub   = 4.05            ni0sub  = 1.1e+016        bg0sub  = 1.17
+nc0sub  = 2.86e+025       nsd     = 2e+026          ngate   = 0               nseg    = 5
+l       = 2.1e-008        xl      = 1e-009          lint    = -2.5e-009       dlc     = 0
+dlbin   = 0               hfin    = 3.2e-008        deltaw  = 0               deltawcv= 0
+sdterm  = 0               epsrsp  = 3.9             nfin    = 1
+toxg    = 1.8e-009
************************************************************
*                            dc                            *
************************************************************
+cit     = 0               cdsc    = 0.003469        cdscd   = 0.001486        dvt0    = 0.05
+dvt1    = 0.36            phin    = 0.05            eta0    = 0.094           dsub    = 0.24
+k1rsce  = 0               lpe0    = 0               dvtshift= 0               qmfactor= 0
+etaqm   = 0.54            qm0     = 2.183e-012      pqm     = 0.66            u0      = 0.0237
+etamob  = 4               up      = 0               ua      = 1.133           eu      = 0.05
+ud      = 0.0105          ucs     = 0.2672          rdswmin = 0               rdsw    = 200
+wr      = 1               rswmin  = 0               rdwmin  = 0               rshs    = 0
+rshd    = 0               vsat    = 60000           deltavsat= 0.17            ksativ  = 1.592
+mexp    = 2.491           ptwg    = 25              pclm    = 0.01            pclmg   = 1
+pdibl1  = 800             pdibl2  = 0.005704        drout   = 4.97            pvag    = 200
+fpitch  = 2.7e-008        rth0    = 0.15            cth0    = 1.243e-006      wth0    = 2.6e-007
+lcdscd  = 0               lcdscdr = 0               lrdsw   = 1.3             lvsat   = 1441
************************************************************
*                         leakage                          *
************************************************************
+aigc    = 0.007           bigc    = 0.0015          cigc    = 1               dlcigs  = 5e-009
+dlcigd  = 5e-009          aigs    = 0.006           aigd    = 0.006           bigs    = 0.001944
+bigd    = 0.001944        cigs    = 1               cigd    = 1               poxedge = 1.152
+agidl   = 2e-012          agisl   = 2e-012          bgidl   = 1.5e+008        bgisl   = 1.5e+008
+egidl   = 1.142           egisl   = 1.142
************************************************************
*                            rf                            *
************************************************************
************************************************************
*                         junction                         *
************************************************************
************************************************************
*                       capacitance                        *
************************************************************
+cfs     = 0               cfd     = 0               cgso    = 1.6e-010        cgdo    = 1.6e-010
+cgsl    = 0               cgdl    = 0               ckappas = 0.6             ckappad = 0.6
+cgbo    = 0               cgbl    = 0
************************************************************
*                       temperature                        *
************************************************************
+tbgasub = 0.000473        tbgbsub = 636             kt1     = 0               kt1l    = 0
+ute     = -1.2            utl     = 0               ua1     = 0.001032        ud1     = 0
+ucste   = -0.004775       at      = 0.001           ptwgt   = 0.004           tmexp   = 0
+prt     = 0               tgidl   = -0.007          igt     = 2.5
************************************************************
*                          noise                           *
************************************************************
**)
.control
pre_osdi /home/sudo-ritish/Desktop/asap_7nm_Xschem/bsimcmg.osdi
.endc



**** end user architecture code
.end
```
</details>

The output plot:

NMOS
![image](https://github.com/user-attachments/assets/0ffbb677-1dc4-480a-99c4-6220040e509d)
Corresponding current values:
![image](https://github.com/user-attachments/assets/7ad8fa64-6a71-4ad9-aff7-8eb15c2c9790)

PMOS
![image](https://github.com/user-attachments/assets/caccb6cf-3128-42c2-84d0-19ce503c0547)
Corresponding current values:
![image](https://github.com/user-attachments/assets/02b6f008-25d1-44de-8c36-32744b605ef3)

## CMOS Inverter Design and Analysis

Now using the above pfet and nfet we can design the basic inverter circuit to perform the dc and transient analysis to characterize the inverter for the ASAP 7nm technology.

The SPICE deck for the inverter circuit was generated through the XSCHEM schematics and was modified to calculate the parameters.

### DC Analysis:
```
** sch_path: /home/hprcse/Finfet/inverter_vtc.sch
**.subckt inverter_vtc
Xpfet1 nfet_out nfet_in vdd vdd asap_7nm_pfet l=7e-009 nfin=1
Xnfet1 nfet_out nfet_in GND GND asap_7nm_nfet l=7e-009 nfin=1
V1 nfet_in GND pulse(0 0.7 20p 10p 10p 20p 500p 1)
V2 vdd GND 0.7
**** begin user architecture code


.dc v1 0 0.7 1m
.control
    run
    set xbrushwidth=3
    plot nfet_out nfet_in
.endc


**** end user architecture code
**.ends
.GLOBAL GND
**** begin user architecture code

.subckt asap_7nm_pfet S G D B l=7e-009 nfin=14
	npmos_finfet S G D B BSIMCMG_osdi_P l=7e-009 nfin=13
.ends asap_7nm_pfet

.model BSIMCMG_osdi_P BSIMCMG_va (
+ TYPE = 0

************************************************************
*                         general                          *
************************************************************
+version = 107             bulkmod = 1               igcmod  = 1               igbmod  = 0
+gidlmod = 1               iimod   = 0               geomod  = 1               rdsmod  = 0
+rgatemod= 0               rgeomod = 0               shmod   = 0               nqsmod  = 0
+coremod = 0               cgeomod = 0               capmod  = 0               tnom    = 25
+eot     = 1e-009          eotbox  = 1.4e-007        eotacc  = 3e-010          tfin    = 6.5e-009
+toxp    = 2.1e-009        nbody   = 1e+022          phig    = 4.9278          epsrox  = 3.9
+epsrsub = 11.9            easub   = 4.05            ni0sub  = 1.1e+016        bg0sub  = 1.17
+nc0sub  = 2.86e+025       nsd     = 2e+026          ngate   = 0               nseg    = 5
+l       = 2.1e-008        xl      = 1e-009          lint    = -2.5e-009       dlc     = 0
+dlbin   = 0               hfin    = 3.2e-008        deltaw  = 0               deltawcv= 0
+sdterm  = 0               epsrsp  = 3.9             nfin    = 1
+toxg    = 1.8e-009
************************************************************
*                            dc                            *
************************************************************
+cit     = 0               cdsc    = 0.003469        cdscd   = 0.001486        dvt0    = 0.05
+dvt1    = 0.36            phin    = 0.05            eta0    = 0.094           dsub    = 0.24
+k1rsce  = 0               lpe0    = 0               dvtshift= 0               qmfactor= 0
+etaqm   = 0.54            qm0     = 2.183e-012      pqm     = 0.66            u0      = 0.0237
+etamob  = 4               up      = 0               ua      = 1.133           eu      = 0.05
+ud      = 0.0105          ucs     = 0.2672          rdswmin = 0               rdsw    = 200
+wr      = 1               rswmin  = 0               rdwmin  = 0               rshs    = 0
+rshd    = 0               vsat    = 60000           deltavsat= 0.17            ksativ  = 1.592
+mexp    = 2.491           ptwg    = 25              pclm    = 0.01            pclmg   = 1
+pdibl1  = 800             pdibl2  = 0.005704        drout   = 4.97            pvag    = 200
+fpitch  = 2.7e-008        rth0    = 0.15            cth0    = 1.243e-006      wth0    = 2.6e-007
+lcdscd  = 0               lcdscdr = 0               lrdsw   = 1.3             lvsat   = 1441
************************************************************
*                         leakage                          *
************************************************************
+aigc    = 0.007           bigc    = 0.0015          cigc    = 1               dlcigs  = 5e-009
+dlcigd  = 5e-009          aigs    = 0.006           aigd    = 0.006           bigs    = 0.001944
+bigd    = 0.001944        cigs    = 1               cigd    = 1               poxedge = 1.152
+agidl   = 2e-012          agisl   = 2e-012          bgidl   = 1.5e+008        bgisl   = 1.5e+008
+egidl   = 1.142           egisl   = 1.142
************************************************************
*                            rf                            *
************************************************************
************************************************************
*                         junction                         *
************************************************************
************************************************************
*                       capacitance                        *
************************************************************
+cfs     = 0               cfd     = 0               cgso    = 1.6e-010        cgdo    = 1.6e-010
+cgsl    = 0               cgdl    = 0               ckappas = 0.6             ckappad = 0.6
+cgbo    = 0               cgbl    = 0
************************************************************
*                       temperature                        *
************************************************************
+tbgasub = 0.000473        tbgbsub = 636             kt1     = 0               kt1l    = 0
+ute     = -1.2            utl     = 0               ua1     = 0.001032        ud1     = 0
+ucste   = -0.004775       at      = 0.001           ptwgt   = 0.004           tmexp   = 0
+prt     = 0               tgidl   = -0.007          igt     = 2.5
************************************************************
*                          noise                           *
************************************************************
**)
.control
pre_osdi /home/sudo-ritish/Desktop/asap_7nm_Xschem/bsimcmg.osdi
.endc



.subckt asap_7nm_nfet S G D B l=7e-009 nfin=14
	nnmos_finfet S G D B BSIMCMG_osdi_N l=7e-009 nfin=13
.ends asap_7nm_nfet

.model BSIMCMG_osdi_N BSIMCMG_va (
+ TYPE = 1
************************************************************
*                         general                          *
************************************************************
+version = 107             bulkmod = 1               igcmod  = 1               igbmod  = 0
+gidlmod = 1               iimod   = 0               geomod  = 1               rdsmod  = 0
+rgatemod= 0               rgeomod = 0               shmod   = 0               nqsmod  = 0
+coremod = 0               cgeomod = 0               capmod  = 0               tnom    = 25
+eot     = 1e-009          eotbox  = 1.4e-007        eotacc  = 1e-010          tfin    = 6.5e-009
+toxp    = 2.1e-009        nbody   = 1e+022          phig    = 4.2466          epsrox  = 3.9
+epsrsub = 11.9            easub   = 4.05            ni0sub  = 1.1e+016        bg0sub  = 1.17
+nc0sub  = 2.86e+025       nsd     = 2e+026          ngate   = 0               nseg    = 5
+l       = 2.1e-008        xl      = 1e-009          lint    = -2e-009         dlc     = 0
+dlbin   = 0               hfin    = 3.2e-008        deltaw  = 0               deltawcv= 0
+sdterm  = 0               epsrsp  = 3.9             nfin    = 1
+toxg    = 1.80e-009
************************************************************
*                            dc                            *
************************************************************
+cit     = 0               cdsc    = 0.01            cdscd   = 0.01            dvt0    = 0.05
+dvt1    = 0.47            phin    = 0.05            eta0    = 0.07            dsub    = 0.35
+k1rsce  = 0               lpe0    = 0               dvtshift= 0               qmfactor= 2.5
+etaqm   = 0.54            qm0     = 0.001           pqm     = 0.66            u0      = 0.0303
+etamob  = 2               up      = 0               ua      = 0.55            eu      = 1.2
+ud      = 0               ucs     = 1               rdswmin = 0               rdsw    = 200
+wr      = 1               rswmin  = 0               rdwmin  = 0               rshs    = 0
+rshd    = 0               vsat    = 70000           deltavsat= 0.2             ksativ  = 2
+mexp    = 4               ptwg    = 30              pclm    = 0.05            pclmg   = 0
+pdibl1  = 0               pdibl2  = 0.002           drout   = 1               pvag    = 0
+fpitch  = 2.7e-008        rth0    = 0.225           cth0    = 1.243e-006      wth0    = 2.6e-007
+lcdscd  = 5e-005          lcdscdr = 5e-005          lrdsw   = 0.2             lvsat   = 0
************************************************************
*                         leakage                          *
************************************************************
+aigc    = 0.014           bigc    = 0.005           cigc    = 0.25            dlcigs  = 1e-009
+dlcigd  = 1e-009          aigs    = 0.0115          aigd    = 0.0115          bigs    = 0.00332
+bigd    = 0.00332         cigs    = 0.35            cigd    = 0.35            poxedge = 1.1
+agidl   = 1e-012          agisl   = 1e-012          bgidl   = 10000000        bgisl   = 10000000
+egidl   = 0.35            egisl   = 0.35
************************************************************
*                            rf                            *
************************************************************
************************************************************
*                         junction                         *
************************************************************
************************************************************
*                       capacitance                        *
************************************************************
+cfs     = 0               cfd     = 0               cgso    = 1.6e-010        cgdo    = 1.6e-010
+cgsl    = 0               cgdl    = 0               ckappas = 0.6             ckappad = 0.6
+cgbo    = 0               cgbl    = 0
************************************************************
*                       temperature                        *
************************************************************
+tbgasub = 0.000473        tbgbsub = 636             kt1     = 0               kt1l    = 0
+ute     = -0.7            utl     = 0               ua1     = 0.001032        ud1     = 0
+ucste   = -0.004775       at      = 0.001           ptwgt   = 0.004           tmexp   = 0
+prt     = 0               tgidl   = -0.007          igt     = 2.5
************************************************************
*                          noise                           *
************************************************************
**)
.control
pre_osdi /home/sudo-ritish/Desktop/asap_7nm_Xschem/bsimcmg.osdi
.endc


**** end user architecture code
.end
```
Output DC Characteristic:

![image](https://github.com/user-attachments/assets/34271ac0-a4dc-4d72-9ee5-5971ddcfb60c)

#### Threshold Voltage

The switching threshold for the inverter can be calculated by using the following command in the SPICE deck inside .control block:
```
.dc v1 0 0.7 1m
.control
    run
    set xbrushwidth=3
    meas dc v_th when nfet_out=nfet_in			
    plot pfet_out pfet_in
.endc
```
Output:
![image](https://github.com/user-attachments/assets/bf1163f8-4b68-4ac0-9a35-4c5ee9352dd2)

#### Gain

The maximum gain can be calculated and be plotted by the following commands in the deck:
```
.dc v1 0 0.7 1m
.control
    run
    set xbrushwidth=3
    meas dc v_th when nfet_out=nfet_in			
    let gain_act = abs(deriv(nfet_out)) > 1				
    plot nfet_out nfet_in
    plot gain_act
.endc
```
Output:
![image](https://github.com/user-attachments/assets/5c70b765-2019-462b-81e5-432ff0d5ea93)

#### Noise Margin

NML = VIL - VOL

NMH = VOH - VIH

The values of VIH, VIL, VOH, VOL can be calculated at the point where the gain value changes to -1. Implementing this logic in the SPICE deck and plotting we can calculate the noise margins.
```
.dc v1 0 0.7 1m
.control
    run
    set xbrushwidth=3
    meas dc v_th when nfet_out=nfet_in			
    let gain_act = abs(deriv(nfet_out)) > 1		
    let gain = (abs(deriv(nfet_out)) >= 1)*0.7		
    plot nfet_out nfet_in
    plot gain_act
    plot nfet_out gain
.endc
```
Output:

*The intersection point gives the values of VIL, VOH, VIH and VOL and hence noise margin can be calculated.
![image](https://github.com/user-attachments/assets/7f992778-49b6-4dea-8b01-896ff3998c08)

#### Current

The current plot can be given as :
![image](https://github.com/user-attachments/assets/5a24b286-c2b7-4978-9e65-c073a313edcc)

### Transient Analysis

For transient analysis the following SPICE netlist has been used:
```
** sch_path: /home/sudo-ritish/Desktop/asap_7nm_Xschem/inverter_finfet.sch
**.subckt inverter_finfet
Xpfet1 nfet_out nfet_in vdd vdd asap_7nm_pfet l=7e-009 nfin=14
Xnfet1 nfet_out nfet_in GND GND asap_7nm_nfet l=7e-009 nfin=14
V1 nfet_in GND pulse(0 0.7 20p 10p 10p 20p 500p 1)
V2 vdd GND 0.7
**** begin user architecture code
.op

.tran 0.1p 100p
.control
    run
    set xbrushwidth=3  
    plot nfet_out nfet_in
.endc
a

**** end user architecture code
**.ends
.GLOBAL GND
**** begin user architecture code

.subckt asap_7nm_pfet S G D B l=7e-009 nfin=14
	npmos_finfet S G D B BSIMCMG_osdi_P l=7e-009 nfin=13
.ends asap_7nm_pfet

.model BSIMCMG_osdi_P BSIMCMG_va (
+ TYPE = 0

************************************************************
*                         general                          *
************************************************************
+version = 107             bulkmod = 1               igcmod  = 1               igbmod  = 0
+gidlmod = 1               iimod   = 0               geomod  = 1               rdsmod  = 0
+rgatemod= 0               rgeomod = 0               shmod   = 0               nqsmod  = 0
+coremod = 0               cgeomod = 0               capmod  = 0               tnom    = 25
+eot     = 1e-009          eotbox  = 1.4e-007        eotacc  = 3e-010          tfin    = 6.5e-009
+toxp    = 2.1e-009        nbody   = 1e+022          phig    = 4.9278          epsrox  = 3.9
+epsrsub = 11.9            easub   = 4.05            ni0sub  = 1.1e+016        bg0sub  = 1.17
+nc0sub  = 2.86e+025       nsd     = 2e+026          ngate   = 0               nseg    = 5
+l       = 2.1e-008        xl      = 1e-009          lint    = -2.5e-009       dlc     = 0
+dlbin   = 0               hfin    = 3.2e-008        deltaw  = 0               deltawcv= 0
+sdterm  = 0               epsrsp  = 3.9             nfin    = 1
+toxg    = 1.8e-009
************************************************************
*                            dc                            *
************************************************************
+cit     = 0               cdsc    = 0.003469        cdscd   = 0.001486        dvt0    = 0.05
+dvt1    = 0.36            phin    = 0.05            eta0    = 0.094           dsub    = 0.24
+k1rsce  = 0               lpe0    = 0               dvtshift= 0               qmfactor= 0
+etaqm   = 0.54            qm0     = 2.183e-012      pqm     = 0.66            u0      = 0.0237
+etamob  = 4               up      = 0               ua      = 1.133           eu      = 0.05
+ud      = 0.0105          ucs     = 0.2672          rdswmin = 0               rdsw    = 200
+wr      = 1               rswmin  = 0               rdwmin  = 0               rshs    = 0
+rshd    = 0               vsat    = 60000           deltavsat= 0.17            ksativ  = 1.592
+mexp    = 2.491           ptwg    = 25              pclm    = 0.01            pclmg   = 1
+pdibl1  = 800             pdibl2  = 0.005704        drout   = 4.97            pvag    = 200
+fpitch  = 2.7e-008        rth0    = 0.15            cth0    = 1.243e-006      wth0    = 2.6e-007
+lcdscd  = 0               lcdscdr = 0               lrdsw   = 1.3             lvsat   = 1441
************************************************************
*                         leakage                          *
************************************************************
+aigc    = 0.007           bigc    = 0.0015          cigc    = 1               dlcigs  = 5e-009
+dlcigd  = 5e-009          aigs    = 0.006           aigd    = 0.006           bigs    = 0.001944
+bigd    = 0.001944        cigs    = 1               cigd    = 1               poxedge = 1.152
+agidl   = 2e-012          agisl   = 2e-012          bgidl   = 1.5e+008        bgisl   = 1.5e+008
+egidl   = 1.142           egisl   = 1.142
************************************************************
*                            rf                            *
************************************************************
************************************************************
*                         junction                         *
************************************************************
************************************************************
*                       capacitance                        *
************************************************************
+cfs     = 0               cfd     = 0               cgso    = 1.6e-010        cgdo    = 1.6e-010
+cgsl    = 0               cgdl    = 0               ckappas = 0.6             ckappad = 0.6
+cgbo    = 0               cgbl    = 0
************************************************************
*                       temperature                        *
************************************************************
+tbgasub = 0.000473        tbgbsub = 636             kt1     = 0               kt1l    = 0
+ute     = -1.2            utl     = 0               ua1     = 0.001032        ud1     = 0
+ucste   = -0.004775       at      = 0.001           ptwgt   = 0.004           tmexp   = 0
+prt     = 0               tgidl   = -0.007          igt     = 2.5
************************************************************
*                          noise                           *
************************************************************
**)
.control
pre_osdi /home/sudo-ritish/Desktop/asap_7nm_Xschem/bsimcmg.osdi
.endc



.subckt asap_7nm_nfet S G D B l=7e-009 nfin=14
	nnmos_finfet S G D B BSIMCMG_osdi_N l=7e-009 nfin=13
.ends asap_7nm_nfet

.model BSIMCMG_osdi_N BSIMCMG_va (
+ TYPE = 1
************************************************************
*                         general                          *
************************************************************
+version = 107             bulkmod = 1               igcmod  = 1               igbmod  = 0
+gidlmod = 1               iimod   = 0               geomod  = 1               rdsmod  = 0
+rgatemod= 0               rgeomod = 0               shmod   = 0               nqsmod  = 0
+coremod = 0               cgeomod = 0               capmod  = 0               tnom    = 25
+eot     = 1e-009          eotbox  = 1.4e-007        eotacc  = 1e-010          tfin    = 6.5e-009
+toxp    = 2.1e-009        nbody   = 1e+022          phig    = 4.2466          epsrox  = 3.9
+epsrsub = 11.9            easub   = 4.05            ni0sub  = 1.1e+016        bg0sub  = 1.17
+nc0sub  = 2.86e+025       nsd     = 2e+026          ngate   = 0               nseg    = 5
+l       = 2.1e-008        xl      = 1e-009          lint    = -2e-009         dlc     = 0
+dlbin   = 0               hfin    = 3.2e-008        deltaw  = 0               deltawcv= 0
+sdterm  = 0               epsrsp  = 3.9             nfin    = 1
+toxg    = 1.80e-009
************************************************************
*                            dc                            *
************************************************************
+cit     = 0               cdsc    = 0.01            cdscd   = 0.01            dvt0    = 0.05
+dvt1    = 0.47            phin    = 0.05            eta0    = 0.07            dsub    = 0.35
+k1rsce  = 0               lpe0    = 0               dvtshift= 0               qmfactor= 2.5
+etaqm   = 0.54            qm0     = 0.001           pqm     = 0.66            u0      = 0.0303
+etamob  = 2               up      = 0               ua      = 0.55            eu      = 1.2
+ud      = 0               ucs     = 1               rdswmin = 0               rdsw    = 200
+wr      = 1               rswmin  = 0               rdwmin  = 0               rshs    = 0
+rshd    = 0               vsat    = 70000           deltavsat= 0.2             ksativ  = 2
+mexp    = 4               ptwg    = 30              pclm    = 0.05            pclmg   = 0
+pdibl1  = 0               pdibl2  = 0.002           drout   = 1               pvag    = 0
+fpitch  = 2.7e-008        rth0    = 0.225           cth0    = 1.243e-006      wth0    = 2.6e-007
+lcdscd  = 5e-005          lcdscdr = 5e-005          lrdsw   = 0.2             lvsat   = 0
************************************************************
*                         leakage                          *
************************************************************
+aigc    = 0.014           bigc    = 0.005           cigc    = 0.25            dlcigs  = 1e-009
+dlcigd  = 1e-009          aigs    = 0.0115          aigd    = 0.0115          bigs    = 0.00332
+bigd    = 0.00332         cigs    = 0.35            cigd    = 0.35            poxedge = 1.1
+agidl   = 1e-012          agisl   = 1e-012          bgidl   = 10000000        bgisl   = 10000000
+egidl   = 0.35            egisl   = 0.35
************************************************************
*                            rf                            *
************************************************************
************************************************************
*                         junction                         *
************************************************************
************************************************************
*                       capacitance                        *
************************************************************
+cfs     = 0               cfd     = 0               cgso    = 1.6e-010        cgdo    = 1.6e-010
+cgsl    = 0               cgdl    = 0               ckappas = 0.6             ckappad = 0.6
+cgbo    = 0               cgbl    = 0
************************************************************
*                       temperature                        *
************************************************************
+tbgasub = 0.000473        tbgbsub = 636             kt1     = 0               kt1l    = 0
+ute     = -0.7            utl     = 0               ua1     = 0.001032        ud1     = 0
+ucste   = -0.004775       at      = 0.001           ptwgt   = 0.004           tmexp   = 0
+prt     = 0               tgidl   = -0.007          igt     = 2.5
************************************************************
*                          noise                           *
************************************************************
**)
.control
pre_osdi /home/sudo-ritish/Desktop/asap_7nm_Xschem/bsimcmg.osdi
.endc


**** end user architecture code
.end
```
Output:

*From this analysis dyanamic parameters such as capacitance, resistance and propagation delays has been calculated.
![image](https://github.com/user-attachments/assets/0625083d-5360-4478-8855-f63e9e8dc9fe)


# Results:
The SPICE simulations provided critical insights into the inverter's performance under the 7nm technology node. The analysis demonstrated reduced power consumption and fast switching times, characteristic of FinFET-based designs, while also highlighting the importance of controlling leakage currents in ultra-scaled technologies.

# Conclusion:
The project successfully demonstrated the use of ASAP 7nm FinFET technology in characterizing an inverter through SPICE simulations. The results confirmed the viability of 7nm FinFETs for designing high-performance, low-power digital circuits, making it a suitable candidate for advanced VLSI designs.
