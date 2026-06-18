# STM32H753VI

`STMicroelectronics STM32H753VI`

![STM32H753VI.jpg](./STM32H753VI.jpg)

```
STM32H7
53VIH6
7BA5B VQ V
PHL 7B 524
.       42
```


### Description

High-performance and DSP with DP-FPU, Arm Cortex-M7 MCU with 2MBytes of Flash memory, 1MB RAM, 480 MHz CPU, L1 cache, external memory interface, JPEG codec, HW crypto, large set of peripherals.

STM32H753xI devices are based on the high-performance Arm® Cortex®-M7 32-bit RISC core operating at up to 480 MHz. The Cortex® -M7 core features a floating point unit (FPU) which supports Arm® double-precision (IEEE 754 compliant) and single-precision data-processing instructions and data types. STM32H753xI devices support a full set of DSP instructions and a memory protection unit (MPU) to enhance application security.

STM32H753xI devices incorporate high-speed embedded memories with a dual-bank flash memory of 2 Mbytes, up to 1 Mbyte of RAM (including 192 Kbytes of TCM RAM, up to 864 Kbytes of user SRAM and 4 Kbytes of backup SRAM), as well as an extensive range of enhanced I/Os and peripherals connected to APB buses, AHB buses, 2x32-bit multi-AHB bus matrix and a multi layer AXI interconnect supporting internal and external memory access.

All the devices offer three ADCs, two DACs, two ultra-low power comparators, a low-power RTC, a high-resolution timer, 12 general-purpose 16-bit timers, two PWM timers for motor control, five low-power timers, a true random number generator (RNG), and a cryptographic acceleration cell. The devices support four digital filters for external sigma-delta modulators (DFSDM). They also feature standard and advanced communication interfaces.


### Artifacts

* [Datasheet](./artifacts/stm32h753vi.pdf)
* [Programming Manual](./artifacts/pm0253-stm32f7-series-and-stm32h7-series-cortexm7-processor-programming-manual-stmicroelectronics.pdf)
* [Reference Manual](./artifacts/rm0433-stm32h742-stm32h743753-and-stm32h750-value-line-advanced-armbased-32bit-mcus-stmicroelectronics.pdf)
* [Errata Sheet](./artifacts/es0392-stm32h742xig-stm32h743xig-stm32h750xb-stm32h753xi-device-errata-stmicroelectronics.pdf)


### MAVProxy

![MAV.jpg](./MAV.jpg)

`$` `mavproxy.py --master=/dev/ttyACM0`

```
Connect /dev/ttyACM0 source_system=255
Log Directory: 
Telemetry log: mav.tlog
Waiting for heartbeat from /dev/ttyACM0
MAV> Detected vehicle 2:1 on link 0
online system 2
STABILIZE> Mode STABILIZE
AP: ArduCopter V4.6.2+WHIV~1.0-WISP3 (a938529f)
AP: ChibiOS: 88b84600
AP: microBlue 0042001D 33335114 30313632
AP: RCOut: Initialising
AP: Frame: QUAD/X
AP: Initialising ArduPilot
AP: Calibrating barometer
Received 1086 parameters
Saved 1072 parameters to mav_2_1.parm
AP: Barometer 1 calibration complete
BMI088: Found device
BMI088: accel config OK (1 tries)
BMI08x: found accel
BMI088: found gyro
BMI088: Found device
BMI08x: delaying accel config
BMI08x: found accel
BMI088: found gyro
Init Gyro*BMI088: accel config OK (4 tries)
***
AP: INS: alloc 6144 bytes for ISB (free=644456)
AP: Scripting: failed to create (/APM/scripts)
AP: TMP117: write to reset failed
AP: ArduPilot Ready
AP: AHRS: DCM active
Failed to create log directory /APM/LOGS : ENOSPC
Log open fail for /APM/LOGS/00000001.BIN - ENOSPC
Log open fail for /APM/LOGS/00000001.BIN - ENOSPC
AP: RCOut: DS600:1-4 PWM:9-12
Lua: State memory usage: 2796 + 5671
AP: Lua: open directory (/APM/scripts) failed
AP: BQ40z80 not found on I2C
AP: EKF3 IMU0 initialised
AP: EKF3 IMU1 initialised
AP: AHRS: EKF3 active
AP: EKF3 IMU1 tilt alignment complete
AP: EKF3 IMU0 tilt alignment complete
Failed to create log directory /APM/LOGS : ENOSPC
AP: BQ40z80 not found on I2C
fence present
fence enabled
Flight battery warning
Failed to create log directory /APM/LOGS : ENOSPC
AP: BQ40z80 not found on I2C
Failed to create log directory /APM/LOGS : ENOSPC
AP: BQ40z80 not found on I2C
Failed to create log directory /APM/LOGS : ENOSPC
Lua: @ROMFS/scripts/BQ40Z_temp_logging.lua:36: calling 'get_device' on bad self (no i2c devices available)
AP: Lua: @ROMFS/scripts/BQ40Z_temp_logging.lua:36: calling 'get_device' on bad self (no i2c devices available)
AP: PreArm: EKF attitude is bad
AP: PreArm: Compass not healthy
AP: PreArm: Battery 1 unhealthy
AP: PreArm: Logging failed
AP: PreArm: Scripting: @ROMFS/scripts/BQ40Z_temp_logging.lua:3
AP: PreArm: Please power cycle: ESC Telemetry Error
AP: PreArm: Fence requires position
```


#### Pulling Parameters

[mav_2_1.param](./artifacts/mav.param)

`MAV>` `param fetch`

```
Requested parameter list (ftp)
Received 1088 parameters (ftp)
```

`MAV>` `param save mav.param`

```
Saved 1088 parameters to mav.param
```


### Firmware Extraction

[STM32H753VI.bin](./artifacts/STM32H753VI.bin)

![FW.jpg](./FW.jpg)

`$` `JLinkExe`

```
SEGGER J-Link Commander V9.24a (Compiled Mar  5 2026 11:04:55)
DLL version V9.24a, compiled Mar  5 2026 11:03:48

Connecting to J-Link via USB...O.K.
Firmware: J-Link Pro V6 compiled Feb 23 2026 11:19:22
Hardware version: V6.00
J-Link uptime (since boot): 0d 00h 05m 10s
S/N: 176002438
License(s): RDI, FlashBP, FlashDL, JFlash, GDB
USB speed mode: High speed (480 MBit/s)
IP-Addr: DHCP (no addr. received yet)
VTref=0.000V


Type "connect" to establish a target connection, '?' for help
```

`J-Link>` `connect`

```
Please specify device / core. <Default>: STM32H753VI
Type '?' for selection dialog
```

`Device>` `?`

```
Please specify target interface:
  J) JTAG (Default)
  S) SWD
  T) cJTAG
```

`TIF>` `s`

```
Specify target interface speed [kHz]. <Default>: 4000 kHz
```

`Speed>`

```
Device "STM32H753VI" selected.


Connecting to target via SWD
ConfigTargetSettings() start
ConfigTargetSettings() end - Took 11us
InitTarget() start
SWD selected. Executing JTAG -> SWD switching sequence.
DAP initialized successfully.
InitTarget() end - Took 3.94ms
Found SW-DP with ID 0x6BA02477
DPIDR: 0x6BA02477
CoreSight SoC-400 or earlier
Scanning AP map to find all available APs
AP[3]: Stopped AP scan as end of AP map has been reached
AP[0]: AHB-AP (IDR: 0x84770001, ADDR: 0x00000000)
AP[1]: AHB-AP (IDR: 0x84770001, ADDR: 0x01000000)
AP[2]: APB-AP (IDR: 0x54770002, ADDR: 0x02000000)
Iterating through AP map to find AHB-AP to use
AP[0]: Core found
AP[0]: AHB-AP ROM base: 0xE00FE000
CPUID register: 0x411FC271. Implementer code: 0x41 (ARM)
Cache: L1 I/D-cache present
Found Cortex-M7 r1p1, Little endian.
FPUnit: 8 code (BP) slots and 0 literal slots
CoreSight components:
ROMTbl[0] @ E00FE000
[0][0]: E00FF000 CID B105100D PID 000BB4C7 ROM Table
ROMTbl[1] @ E00FF000
[1][0]: E000E000 CID B105E00D PID 000BB00C SCS-M7
[1][1]: E0001000 CID B105E00D PID 000BB002 DWT
[1][2]: E0002000 CID B105E00D PID 000BB00E FPB-M7
[1][3]: E0000000 CID B105E00D PID 000BB001 ITM
[0][1]: E0041000 CID B105900D PID 001BB975 ETM-M7
[0][2]: E0043000 CID B105900D PID 004BB906 CTI
I-Cache L1: 16 KB, 256 Sets, 32 Bytes/Line, 2-Way
D-Cache L1: 16 KB, 128 Sets, 32 Bytes/Line, 4-Way
Memory zones:
  Zone: "Default" Description: Default access mode
Cortex-M7 identified.

****** Error: CPU is not halted
```

`J-Link>` `halt`

```
PC = 0800798A, CycleCnt = FB2EF62F
R0 = 0000000C, R1 = A2F02FAC, R2 = E0001000, R3 = 80000001
R4 = 40080000, R5 = 2000604C, R6 = 40080000, R7 = 20004460
R8 = 00000000, R9 = 00000000, R10= 00000000, R11= 00000000
R12= 00000000
SP(R13)= 200021C0, MSP= 20000600, PSP= 200021C0, R14(LR) = 08007989
XPSR = 81000000: APSR = Nzcvq, EPSR = 01000000, IPSR = 000 (NoException)
CFBP = 06003000, CONTROL = 06, FAULTMASK = 00, BASEPRI = 30, PRIMASK = 00

FPS0 = 00000000, FPS1 = 00000000, FPS2 = 00000000, FPS3 = 00000000
FPS4 = 00000000, FPS5 = 00000000, FPS6 = 00000000, FPS7 = 00000000
FPS8 = 00000000, FPS9 = 08008E6D, FPS10= 00000000, FPS11= 00000000
FPS12= 00000000, FPS13= 00000000, FPS14= 00000000, FPS15= 00000000
FPS16= 00000000, FPS17= 00000000, FPS18= 00000000, FPS19= 00000000
FPS20= 00000000, FPS21= 00000000, FPS22= 00000000, FPS23= 00000000
FPS24= 00000000, FPS25= 00000000, FPS26= 00000000, FPS27= 00000000
FPS28= 00000000, FPS29= 00000000, FPS30= 00000000, FPS31= FFFFFFFF
FPSCR= 00000000
```

`J-Link>` `savebin STM32H753VI.bin 0x08000000 0x200000`

```
Opening binary file for writing... [STM32H753VI.bin]
Reading 2097152 bytes from addr 0x08000000 into file...O.K.
```


### Sources

* [https://www.st.com/en/microcontrollers-microprocessors/stm32h753vi.html](https://www.st.com/en/microcontrollers-microprocessors/stm32h753vi.html)

* [https://github.com/ArduPilot/ardupilot](https://github.com/ArduPilot/ardupilot)

* [https://github.com/ardupilot/mavproxy](https://github.com/ardupilot/mavproxy)

* [https://www.segger.com/products/debug-probes/j-link/tools/j-link-commander/](https://www.segger.com/products/debug-probes/j-link/tools/j-link-commander/)

* [https://kb.segger.com/J-Link_Commander](https://kb.segger.com/J-Link_Commander)

