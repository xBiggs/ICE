# GS041033

`Standalone LoRa PCB R05`

![GS041033Front.jpg](./GS041033Front.jpg)

![GS041033Back.jpg](./GS041033Back.jpg)

```
GS041033 R04
```


### Components

* 1 x [ESP32-S3FN8](./ESP32S3FN8/README.md)
* 1 x [SKY66122-11](./SKY6612211/README.md)
* 1 x [LR1121](./LR1121/README.md)


### Description

A custom wireless communications PCB.


### Interfaces

* 1 x Micro USB
* 1 x 2.4 GHz 802.11 b/g/n Wi-Fi / 2.4 GHz Bluetooth 5 LE Antenna
* 1 x 2.4 GHz LoRa Antenna
* 1 x 915 MHz LoRa Antenna
* 1 x Expansion Port
* 1 x UART


### Bootup

`$` `sudo screen -L /dev/ttyACM0 115200`

`GS9000>` `restart`

```
I (227265) wifi:flush txq
I (227265) wifi:stop sw txq
I (227265) wifi:lmac stop hw txq
ESP-ROM:esp32s3-20210327
Build:Mar 27 2021
rst:0xc (RTC_SW_CPU_RST),boot:0x8 (SPI_FAST_FLASH_BOOT)
Saved PC:0x42004779
SPIWP:0xee
mode:DIO, clock div:1
load:0x3fce3808,len:0x1658
load:0x403c9700,len:0xbc0
load:0x403cc700,len:0x2f3c
entry 0x403c9950
I (24) boot: ESP-IDF v4.4.6 2nd stage bootloader
I (24) boot: compile time 17:33:18
I (24) boot: Multicore bootloader
I (26) boot: chip revision: v0.2
I (30) boot.esp32s3: Boot SPI Speed : 80MHz
I (35) boot.esp32s3: SPI Mode       : DIO
I (39) boot.esp32s3: SPI Flash Size : 8MB
I (44) boot: Enabling RNG early entropy source...
I (50) boot: Partition Table:
I (53) boot: ## Label            Usage          Type ST Offset   Length
I (60) boot:  0 nvs              WiFi data        01 02 00009000 00004000
I (68) boot:  1 otadata          OTA data         01 00 0000d000 00002000
I (75) boot:  2 phy_init         RF data          01 01 0000f000 00001000
I (83) boot:  3 ota_0            OTA app          00 10 00100000 00380000
I (90) boot:  4 ota_1            OTA app          00 11 00480000 00380000
I (98) boot: End of partition table
I (102) esp_image: segment 0: paddr=00480020 vaddr=3c0f0020 size=41010h (266256) map
I (158) esp_image: segment 1: paddr=004c1038 vaddr=3fc9d190 size=04650h ( 18000) load
I (163) esp_image: segment 2: paddr=004c5690 vaddr=40374000 size=0a988h ( 43400) load
I (174) esp_image: segment 3: paddr=004d0020 vaddr=42000020 size=ee7d4h (976852) map
I (350) esp_image: segment 4: paddr=005be7fc vaddr=4037e988 size=0e804h ( 59396) load
I (373) boot: Loaded app from partition at offset 0x480000
I (374) boot: Disabling RNG early entropy source...
I (375) cpu_start: Multicore app
I (378) cpu_start: Pro cpu up.
I (382) cpu_start: Starting app cpu, entry point is 0x403755fc
I (370) cpu_start: App cpu up.
I (397) cpu_start: Pro cpu start user code
I (397) cpu_start: cpu freq: 160000000
I (397) cpu_start: Application information:
I (397) cpu_start: Project name:     db_esp32
I (398) cpu_start: App version:      0.8.13
I (398) cpu_start: Compile time:     May  8 2026 16:27:20
I (398) cpu_start: ELF file SHA256:  406b3db9b16450f1...
I (398) cpu_start: ESP-IDF:          v4.4.6
I (399) cpu_start: Min chip rev:     v0.0
I (399) cpu_start: Max chip rev:     v0.99
I (399) cpu_start: Chip rev:         v0.2
I (399) heap_init: Initializing. RAM available for dynamic allocation:
I (400) heap_init: At 3FCB8528 len 000311E8 (196 KiB): D/IRAM
I (400) heap_init: At 3FCE9710 len 00005724 (21 KiB): STACK/DIRAM
I (400) heap_init: At 3FCF0000 len 00008000 (32 KiB): DRAM
I (401) heap_init: At 600FE000 len 00002000 (8 KiB): RTCRAM
I (402) spi_flash: detected chip: generic
I (402) spi_flash: flash io: dio
I (403) sleep: Configure to isolate all GPIO pins in sleep state
I (404) sleep: Enable automatic switching of GPIO sleep configuration
I (404) coexist: coexist rom version e7ae62f
I (405) cpu_start: Starting scheduler on PRO CPU.
I (0) cpu_start: Starting scheduler on APP CPU.
I (405) DB_ESP32: Firmware version: 0.8.13
I (405) DB_ESP32: Board revision target: R4
I (405) DB_ESP32: OTA state: 4294967295
I (405) DB_ESP32: Running partition type 0 subtype 17 (offset 0x00480000)
I (445) Config API: Initializing NVS flash
I (585) Config API: Finished initializing NVS flash
I (585) DB_ESP32: Configuring SPI (bus 2, freq 5000000, clk 36, mosi 35, miso 37)
I (595) DB_ESP32: Initting sensors, etc
I (595) gpio: GPIO[7]| InputEn: 0| OutputEn: 1| OpenDrain: 0| Pullup: 0| Pulldown: 0| Intr:0
I (595) gpio: GPIO[48]| InputEn: 0| OutputEn: 1| OpenDrain: 0| Pullup: 0| Pulldown: 0| Intr:0
I (595) DB_ESP32: Starting LR1110 endpoint
I (595) LR11XX: Initializing lr1110 (busy: 47, nss 34, irq 5, reset 6)
I (595) gpio: GPIO[34]| InputEn: 0| OutputEn: 1| OpenDrain: 0| Pullup: 0| Pulldown: 0| Intr:0
I (595) gpio: GPIO[6]| InputEn: 0| OutputEn: 1| OpenDrain: 0| Pullup: 0| Pulldown: 0| Intr:0
I (595) gpio: GPIO[47]| InputEn: 1| OutputEn: 0| OpenDrain: 0| Pullup: 0| Pulldown: 0| Intr:0
I (595) gpio: GPIO[5]| InputEn: 1| OutputEn: 0| OpenDrain: 0| Pullup: 0| Pulldown: 0| Intr:1
I (595) LR11XX: LR11XX driver version: v2.2.0
I (3275) LR11XX: LR11xx information:
I (3275) LR11XX:   - Firmware = 0x0101
I (3275) LR11XX:   - Hardware = 0x22
I (3275) LR11XX:   - Type     = 0x03 (0x01 for LR1110, 0x02 for LR1120, 0x03 for LR1121)
I (3275) LR11XX: Common parameters:
I (3275) LR11XX:    Packet type   = LORA
I (3275) LR11XX:    RF frequency  = 915000000 Hz
I (3275) LR11XX:    Output power  = 14 dBm
I (3275) LR11XX:    Fallback mode = 1
I (3275) LR11XX:    Rx boost deactivated
I (3275) LR11XX: LoRa modulation parameters:
I (3285) LR11XX:    Spreading factor = 7
I (3285) LR11XX:    Bandwidth        = 6
I (3285) LR11XX:    Coding rate      = 1
I (3285) LR11XX: LoRa packet parameters:
I (3285) LR11XX:    Preamble length = 8 symbol(s)
I (3285) LR11XX:    Header mode     = 0
I (3285) LR11XX:    Payload length  = 255 byte(s)
I (3285) LR11XX:    CRC mode        = 1
I (3285) LR11XX:    IQ              = 1
I (3285) LR11XX: LoRa syncword = 0x12
I (3285) LR11XX: Initialized lr1110
I (3285) WATCHDOG: Watchdog task created, watchdog counter is at 0
I (3285) WATCHDOG: Watchdog Task Started. Will check interrupt pin every 1 second. Threshold: 5
I (3285) LR1110_EP: Starting lr1110 rx
I (3285) DB_ESP32: Initting WIFI
I (3285) gpio: GPIO[9]| InputEn: 0| OutputEn: 0| OpenDrain: 0| Pullup: 1| Pulldown: 0| Intr:0
I (3285) gpio: GPIO[8]| InputEn: 0| OutputEn: 0| OpenDrain: 0| Pullup: 1| Pulldown: 0| Intr:0
I (3285) pp: pp rom version: e7ae62f
I (3285) net80211: net80211 rom version: e7ae62f
I (3295) wifi:wifi driver task: 3fcf7e44, prio:23, stack:6656, core=0
I (3295) system_api: Base MAC address is not set
I (3295) system_api: read default base MAC address from EFUSE
I (3305) wifi:wifi firmware version: 1ba8b6a
I (3305) wifi:wifi certification version: v7.0
I (3305) wifi:config NVS flash: enabled
I (3305) wifi:config nano formating: disabled
I (3305) wifi:Init data frame dynamic rx buffer num: 32
I (3305) wifi:Init management frame dynamic rx buffer num: 32
I (3305) wifi:Init management short buffer num: 32
I (3305) wifi:Init dynamic tx buffer num: 32
I (3305) wifi:Init static tx FG buffer num: 2
I (3305) wifi:Init static rx buffer size: 1600
I (3315) wifi:Init static rx buffer num: 10
I (3315) wifi:Init dynamic rx buffer num: 32
I (3315) wifi_init: rx ba win: 6
I (3315) wifi_init: tcpip mbox: 32
I (3315) wifi_init: udp mbox: 6
I (3315) wifi_init: tcp mbox: 6
I (3315) wifi_init: tcp tx win: 5744
I (3315) wifi_init: tcp rx win: 5744
I (3315) wifi_init: tcp mss: 1440
I (3315) wifi_init: WiFi IRAM OP enabled
I (3315) wifi_init: WiFi RX IRAM OP enabled
I (3325) phy_init: phy_version 610,2bff4c8,Jul 27 2023,20:22:14
I (3355) wifi:mode : sta (90:70:69:1d:f6:fc)
I (3355) wifi:enable tsf
I (3355) wifi:Set ps type: 0
I (3365) WIFI: wifi_init_sta finished.
I (3365) log_server: Opened UDP socket on port 5580
I (3365) DB_ESP32: Set hostname to: "wisp_058"
I (3375) DB_ESP32: Starting control module
I (3375) DB_CONTROL: Started Control Module
I (3375) gpio: GPIO[16]| InputEn: 0| OutputEn: 1| OpenDrain: 0| Pullup: 0| Pulldown: 0| Intr:0
I (3375) gpio: GPIO[21]| InputEn: 1| OutputEn: 0| OpenDrain: 0| Pullup: 0| Pulldown: 0| Intr:0
I (3375) DB_CONTROL: Opened UDP socket on port 14550
I (3375) DB_CONTROL: Starting control_module task loop
I (3375) DB_HTTP_REST: Starting Rest API
I (3375) DB_HTTP_REST: Starting HTTP Server
I (3375) DB_ESP32: Running CLI
I (5775) WIFI: Startup retry 1/7
I (8185) WIFI: Startup retry 2/7
I (10595) WIFI: Startup retry 3/7
I (13005) WIFI: Startup retry 4/7
I (15425) WIFI: Startup retry 5/7
I (17835) WIFI: Startup retry 6/7
I (20245) WIFI: Startup retry 7/7
W (22655) WIFI: Startup failed. Transitioning to FAILOVER (SoftAP ON).
I (22655) wifi:mode : sta (90:70:69:1d:f6:fc) + softAP (90:70:69:1d:f6:fd)
I (22665) wifi:Total power save buffer number: 16
I (22665) wifi:Init max length of beacon: 752/752
I (22665) wifi:Init max length of beacon: 752/752
```


### Firmware Extraction

[ESP32S3FN8.bin](./artifacts/ESP32S3FN8.bin)

![FW.jpg](./FW.jpg)

`$` `esptool -p /dev/ttyACM0 -b 115200 --no-stub --before default-reset --after hard-reset --chip esp32s3 read-flash 0x00000 0x800000 ESP32S3FN8.bin`
```
esptool v5.3.0
Connected to ESP32-S3 on /dev/ttyACM0:
Chip type:          ESP32-S3 (QFN56) (revision v0.2)
Features:           Wi-Fi, BT 5 (LE), Dual Core + LP Core, 240MHz, Embedded Flash 8MB (XMC)
Crystal frequency:  40MHz
USB mode:           USB-Serial/JTAG
MAC:                90:70:69:1d:f7:a8


Enabling default SPI flash mode...
Configuring flash size...
Note: In case of failure, please set a specific flash size.
Read 8388608 bytes from 0x00000000 in 124.6 seconds (538.7 kbit/s) to 'ESP32S3FN8.bin'.

Hard resetting via RTS pin...
```

`$` `esptool image-info ESP32S3FN8.bin`

```
esptool v5.3.0
Image size: 4194304 bytes
Detected image type: ESP32-S3

ESP32-S3 Image Header
=====================
Image version: 1
Entry point: 0x403c9950
Segments: 3
Flash size: 8MB
Flash freq: 80m
Flash mode: DIO

ESP32-S3 Extended Image Header
==============================
WP pin: 0xee (disabled)
Flash pins drive settings: clk_drv: 0x0, q_drv: 0x0, d_drv: 0x0, cs0_drv: 0x0, hd_drv: 0x0, wp_drv: 0x0
Chip ID: 9 (ESP32-S3)
Minimal chip revision: v0.0, (legacy min_rev = 0)
Maximal chip revision: v0.99

Segments Information
====================
Segment   Length   Load addr   File offs  Memory types
-------  -------  ----------  ----------  ------------
      0  0x01658  0x3fce3808  0x00000018  BYTE_ACCESSIBLE, MEM_INTERNAL, DRAM
      1  0x00bc0  0x403c9700  0x00001678  MEM_INTERNAL, IRAM
      2  0x02f3c  0x403cc700  0x00002240  MEM_INTERNAL, IRAM

ESP32-S3 Image Footer
=====================
Checksum: 0xaf (valid)
Validation hash: 4e25824e9cfcf0d978a9c714763f107e3051556f29475f894ade4893ff837d63 (valid)
```


### Sources

* [https://github.com/espressif/esp-idf](https://github.com/espressif/esp-idf)
* [https://github.com/espressif/esptool](https://github.com/espressif/esptool)

