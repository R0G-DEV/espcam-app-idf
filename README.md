# Using ESPCAM With ESP-IDF

## Overview
Creates a http server and listens to `GET` requests at `http://[board-ip]/jpg`

## Instructions
    git clone https://github.com/espressif/esp-idf --recursive esp-idf
    git clone https://github.com/R0G-DEV/espcam-app-idf.git

Configure your WiFi SSID and Password in `Kconfig.projbuild`

    idf.py build
    idf.py flash
    idf.py monitor
    
## Output

    $ idf.py monitor
    --- idf_monitor on COM10 115200 ---
    ets Jun  8 2016 00:22:57

    rst:0x1 (POWERON_RESET),boot:0x13 (SPI_FAST_FLASH_BOOT)
    configsip: 0, SPIWP:0xee
    clk_drv:0x00,q_drv:0x00,d_drv:0x00,cs0_drv:0x00,hd_drv:0x00,wp_drv:0x00
    mode:DIO, clock div:2
    load:0x3fff0018,len:4
    load:0x3fff001c,len:6428
    load:0x40078000,len:11368
    load:0x40080400,len:6644
    entry 0x4008076c
    I (28) boot: ESP-IDF v4.0-dev-1381-g6fe853a2c-dirty 2nd stage bootloader
    I (29) boot: compile time 13:33:48
    I (30) boot: Enabling RNG early entropy source...
    I (35) boot: SPI Speed      : 40MHz
    I (39) boot: SPI Mode       : DIO
    I (43) boot: SPI Flash Size : 2MB
    I (47) boot: Partition Table:
    I (51) boot: ## Label            Usage          Type ST Offset   Length
    I (58) boot:  0 nvs              WiFi data        01 02 00009000 00006000
    I (66) boot:  1 phy_init         RF data          01 01 0000f000 00001000
    I (73) boot:  2 factory          factory app      00 00 00010000 00100000
    I (81) boot: End of partition table
    I (85) esp_image: segment 0: paddr=0x00010020 vaddr=0x3f400020 size=0x1d09c (118940) map
    I (136) esp_image: segment 1: paddr=0x0002d0c4 vaddr=0x3ffb0000 size=0x02f4c ( 12108) load
    I (141) esp_image: segment 2: paddr=0x00030018 vaddr=0x400d0018 size=0x76f6c (487276) map
    0x400d0018: _stext at ??:?

    I (317) esp_image: segment 3: paddr=0x000a6f8c vaddr=0x3ffb2f4c size=0x004d8 (  1240) load
    I (318) esp_image: segment 4: paddr=0x000a746c vaddr=0x40080000 size=0x00400 (  1024) load
    0x40080000: _WindowOverflow4 at F:/IOT/esp-idf/idf/components/freertos/xtensa_vectors.S:1778

    I (324) esp_image: segment 5: paddr=0x000a7874 vaddr=0x40080400 size=0x10cd8 ( 68824) load
    I (372) boot: Loaded app from partition at offset 0x10000
    I (373) boot: Disabling RNG early entropy source...
    I (373) cpu_start: Pro cpu up.
    I (377) cpu_start: Application information:
    I (381) cpu_start: Project name:     esp32_cam_http_jpg
    I (387) cpu_start: App version:      f6ba9df-dirty
    I (393) cpu_start: Compile time:     Aug  9 2019 13:33:30
    I (399) cpu_start: ELF file SHA256:  2cd0991ff29ed3f5...
    I (405) cpu_start: ESP-IDF:          v4.0-dev-1381-g6fe853a2c-dirty
    I (412) cpu_start: Starting app cpu, entry point is 0x40081188
    0x40081188: call_start_cpu1 at F:/IOT/esp-idf/idf/components/esp32/cpu_start.c:281

    I (0) cpu_start: App cpu up.
    D (422) memory_layout: Checking 7 reserved memory ranges:
    D (427) memory_layout: Reserved memory range 0x3ffae000 - 0x3ffae6e0
    D (434) memory_layout: Reserved memory range 0x3ffb0000 - 0x3ffb9388
    D (440) memory_layout: Reserved memory range 0x3ffe0000 - 0x3ffe0440
    D (447) memory_layout: Reserved memory range 0x3ffe3f20 - 0x3ffe4350
    D (453) memory_layout: Reserved memory range 0x40070000 - 0x40078000
    D (459) memory_layout: Reserved memory range 0x40078000 - 0x40080000
    0x40080000: _WindowOverflow4 at F:/IOT/esp-idf/idf/components/freertos/xtensa_vectors.S:1778

    D (466) memory_layout: Reserved memory range 0x40080000 - 0x400910d5
    0x40080000: _WindowOverflow4 at F:/IOT/esp-idf/idf/components/freertos/xtensa_vectors.S:1778

    D (472) memory_layout: Building list of available memory regions:
    D (479) memory_layout: Available memory region 0x3ffae6e0 - 0x3ffb0000
    D (485) memory_layout: Available memory region 0x3ffb9388 - 0x3ffc0000
    D (492) memory_layout: Available memory region 0x3ffc0000 - 0x3ffc2000
    D (498) memory_layout: Available memory region 0x3ffc2000 - 0x3ffc4000
    D (505) memory_layout: Available memory region 0x3ffc4000 - 0x3ffc6000
    D (511) memory_layout: Available memory region 0x3ffc6000 - 0x3ffc8000
    D (518) memory_layout: Available memory region 0x3ffc8000 - 0x3ffca000
    D (525) memory_layout: Available memory region 0x3ffca000 - 0x3ffcc000
    D (531) memory_layout: Available memory region 0x3ffcc000 - 0x3ffce000
    D (538) memory_layout: Available memory region 0x3ffce000 - 0x3ffd0000
    D (544) memory_layout: Available memory region 0x3ffd0000 - 0x3ffd2000
    D (551) memory_layout: Available memory region 0x3ffd2000 - 0x3ffd4000
    D (558) memory_layout: Available memory region 0x3ffd4000 - 0x3ffd6000
    D (564) memory_layout: Available memory region 0x3ffd6000 - 0x3ffd8000
    D (571) memory_layout: Available memory region 0x3ffd8000 - 0x3ffda000
    D (577) memory_layout: Available memory region 0x3ffda000 - 0x3ffdc000
    D (584) memory_layout: Available memory region 0x3ffdc000 - 0x3ffde000
    D (591) memory_layout: Available memory region 0x3ffde000 - 0x3ffe0000
    D (597) memory_layout: Available memory region 0x3ffe0440 - 0x3ffe3f20
    D (604) memory_layout: Available memory region 0x3ffe4350 - 0x3ffe8000
    D (610) memory_layout: Available memory region 0x3ffe8000 - 0x3fff0000
    D (617) memory_layout: Available memory region 0x3fff0000 - 0x3fff8000
    D (624) memory_layout: Available memory region 0x3fff8000 - 0x3fffc000
    D (630) memory_layout: Available memory region 0x3fffc000 - 0x40000000
    D (637) memory_layout: Available memory region 0x400910d8 - 0x40092000
    D (643) memory_layout: Available memory region 0x40092000 - 0x40094000
    D (650) memory_layout: Available memory region 0x40094000 - 0x40096000
    D (657) memory_layout: Available memory region 0x40096000 - 0x40098000
    D (663) memory_layout: Available memory region 0x40098000 - 0x4009a000
    D (670) memory_layout: Available memory region 0x4009a000 - 0x4009c000
    D (676) memory_layout: Available memory region 0x4009c000 - 0x4009e000
    D (683) memory_layout: Available memory region 0x4009e000 - 0x400a0000
    I (690) heap_init: Initializing. RAM available for dynamic allocation:
    D (697) heap_init: New heap initialised at 0x3ffae6e0
    I (702) heap_init: At 3FFAE6E0 len 00001920 (6 KiB): DRAM
    D (708) heap_init: New heap initialised at 0x3ffb9388
    I (713) heap_init: At 3FFB9388 len 00026C78 (155 KiB): DRAM
    I (719) heap_init: At 3FFE0440 len 00003AE0 (14 KiB): D/IRAM
    I (726) heap_init: At 3FFE4350 len 0001BCB0 (111 KiB): D/IRAM
    D (732) heap_init: New heap initialised at 0x400910d8
    I (737) heap_init: At 400910D8 len 0000EF28 (59 KiB): IRAM
    I (743) cpu_start: Pro cpu start user code
    D (755) clk: RTC_SLOW_CLK calibration value: 3401562
    V (765) intr_alloc: esp_intr_alloc_intrstatus (cpu 0): checking args
    V (765) intr_alloc: esp_intr_alloc_intrstatus (cpu 0): Args okay. Resulting flags 0xC0E
    D (770) intr_alloc: Connected src 57 to int 2 (cpu 0)
    V (776) intr_alloc: esp_intr_alloc_intrstatus (cpu 0): checking args
    V (781) intr_alloc: esp_intr_alloc_intrstatus (cpu 0): Args okay. Resulting flags 0x40E
    D (790) intr_alloc: Connected src 24 to int 3 (cpu 0)
    D (795) FLASH_HAL: extra_dummy: 1
    D (798) spi_flash: trying chip: issi
    D (802) spi_flash: trying chip: generic
    I (806) spi_flash: detected chip: generic
    I (810) spi_flash: flash io: dio
    W (814) spi_flash: Detected size(4096k) larger than the size in the binary image header(2048k). Using the size in the binary image header.
    I (828) cpu_start: Starting scheduler on PRO CPU.
    V (0) intr_alloc: esp_intr_alloc_intrstatus (cpu 1): checking args
    V (0) intr_alloc: esp_intr_alloc_intrstatus (cpu 1): Args okay. Resulting flags 0x40E
    D (10) intr_alloc: Connected src 25 to int 2 (cpu 1)
    I (10) cpu_start: Starting scheduler on APP CPU.
    D (877) heap_init: New heap initialised at 0x3ffe0440
    D (877) heap_init: New heap initialised at 0x3ffe4350
    V (887) intr_alloc: esp_intr_alloc_intrstatus (cpu 0): checking args
    V (887) intr_alloc: esp_intr_alloc_intrstatus (cpu 0): Args okay. Resulting flags 0xE
    D (887) intr_alloc: Connected src 16 to int 9 (cpu 0)
    D (907) nvs: nvs_flash_init_custom partition=nvs start=9 count=6
    D (937) camera: Enabling XCLK output
    D (937) ledc: LEDC_PWM CHANNEL 0|GPIO 00|Duty 0002|Time 0
    D (947) camera: Initializing SSCB
    D (947) camera: Resetting camera by power down line
    I (947) gpio: GPIO[32]| InputEn: 0| OutputEn: 1| OpenDrain: 0| Pullup: 0| Pulldown: 0| Intr:0
    D (977) camera: Resetting via SCCB
    D (987) camera: Searching for camera address
    D (997) camera: Detected camera at address=0x30
    D (1007) camera: Camera PID=0x26 VER=0x42 MIDL=0x7f MIDH=0xa2
    D (1007) ov2640: OV2640 Attached
    D (1007) camera: Doing SW reset of sensor
    D (1047) camera: Detected OV2640 camera
    D (1047) camera: in_bpp: 2, fb_bpp: 2, fb_size: 60000, mode: 3, width: 800 height: 600
    I (1047) gpio: GPIO[35]| InputEn: 1| OutputEn: 0| OpenDrain: 0| Pullup: 1| Pulldown: 0| Intr:0
    I (1057) gpio: GPIO[34]| InputEn: 1| OutputEn: 0| OpenDrain: 0| Pullup: 1| Pulldown: 0| Intr:0
    I (1067) gpio: GPIO[39]| InputEn: 1| OutputEn: 0| OpenDrain: 0| Pullup: 1| Pulldown: 0| Intr:0
    I (1077) gpio: GPIO[36]| InputEn: 1| OutputEn: 0| OpenDrain: 0| Pullup: 1| Pulldown: 0| Intr:0
    I (1087) gpio: GPIO[21]| InputEn: 1| OutputEn: 0| OpenDrain: 0| Pullup: 1| Pulldown: 0| Intr:0
    I (1097) gpio: GPIO[19]| InputEn: 1| OutputEn: 0| OpenDrain: 0| Pullup: 1| Pulldown: 0| Intr:0
    I (1107) gpio: GPIO[18]| InputEn: 1| OutputEn: 0| OpenDrain: 0| Pullup: 1| Pulldown: 0| Intr:0
    I (1117) gpio: GPIO[5]| InputEn: 1| OutputEn: 0| OpenDrain: 0| Pullup: 1| Pulldown: 0| Intr:0
    I (1127) gpio: GPIO[25]| InputEn: 1| OutputEn: 0| OpenDrain: 0| Pullup: 1| Pulldown: 0| Intr:0
    I (1137) gpio: GPIO[23]| InputEn: 1| OutputEn: 0| OpenDrain: 0| Pullup: 1| Pulldown: 0| Intr:0
    I (1147) gpio: GPIO[22]| InputEn: 1| OutputEn: 0| OpenDrain: 0| Pullup: 1| Pulldown: 0| Intr:0
    V (1147) intr_alloc: esp_intr_alloc_intrstatus (cpu 0): checking args
    V (1157) intr_alloc: esp_intr_alloc_intrstatus (cpu 0): Args okay. Resulting flags 0xC02
    D (1167) intr_alloc: Connected src 32 to int 12 (cpu 0)
    D (1167) camera: Line width (for DMA): 6400 bytes
    D (1177) camera: DMA buffer size: 3200, DMA buffers per line: 2
    D (1187) camera: DMA buffer count: 8
    D (1187) camera: DMA buffer total: 25600 bytes
    D (1187) camera: Allocating DMA buffer #0, size=3200
    D (1197) camera: Allocating DMA buffer #1, size=3200
    D (1197) camera: Allocating DMA buffer #2, size=3200
    D (1207) camera: Allocating DMA buffer #3, size=3200
    D (1207) camera: Allocating DMA buffer #4, size=3200
    D (1217) camera: Allocating DMA buffer #5, size=3200
    D (1217) camera: Allocating DMA buffer #6, size=3200
    D (1227) camera: Allocating DMA buffer #7, size=3200
    I (1227) camera: Allocating 1 frame buffers (58 KB total)
    I (1237) camera: Allocating 58 KB frame buffer in OnBoard RAM
    V (1247) intr_alloc: esp_intr_alloc_intrstatus (cpu 0): checking args
    V (1247) intr_alloc: esp_intr_alloc_intrstatus (cpu 0): Args okay. Resulting flags 0x402
    D (1247) intr_alloc: Connected src 22 to int 13 (cpu 0)
    D (1267) camera: gpio_install_isr_service state (0)
    D (1267) camera: Setting frame size to 800x600
    D (1447) event: running task for loop 0x3ffd4640
    D (1447) event: created task for loop 0x3ffd4640
    D (1447) event: created event loop 0x3ffd4640
    D (1457) nvs: nvs_open_from_partition misc 1
    D (1457) nvs: nvs_get_str_or_blob log
    D (1457) nvs: nvs_erase_key log
    D (1467) nvs: nvs_get_str_or_blob log
    D (1467) nvs: nvs_set_blob log 24
    I (1487) wifi: wifi driver task: 3ffd6cb0, prio:23, stack:3584, core=0
    D (1647) nvs: nvs_open_from_partition nvs.net80211 1
    D (1647) nvs: nvs_get opmode 1
    D (1647) nvs: nvs_get_str_or_blob sta.ssid
    D (1657) nvs: nvs_get_str_or_blob sta.mac
    D (1657) nvs: nvs_get sta.authmode 1
    D (1667) nvs: nvs_get_str_or_blob sta.pswd
    D (1667) nvs: nvs_get_str_or_blob sta.pmk
    D (1667) nvs: nvs_get sta.chan 1
    D (1677) nvs: nvs_get auto.conn 1
    D (1677) nvs: nvs_get bssid.set 1
    D (1677) nvs: nvs_get_str_or_blob sta.bssid
    D (1687) nvs: nvs_get sta.lis_intval 2
    D (1687) nvs: nvs_get sta.phym 1
    D (1687) nvs: nvs_get sta.phybw 1
    D (1697) nvs: nvs_get_str_or_blob sta.apsw
    D (1697) nvs: nvs_get_str_or_blob sta.apinfo
    D (1707) nvs: nvs_get sta.scan_method 1
    D (1707) nvs: nvs_get sta.sort_method 1
    D (1707) nvs: nvs_get sta.minrssi 1
    D (1717) nvs: nvs_get sta.minauth 1
    D (1717) nvs: nvs_get_str_or_blob ap.ssid
    D (1727) nvs: nvs_get_str_or_blob ap.mac
    D (1727) nvs: nvs_get_str_or_blob ap.passwd
    D (1727) nvs: nvs_get_str_or_blob ap.pmk
    D (1737) nvs: nvs_get ap.chan 1
    D (1737) nvs: nvs_get ap.authmode 1
    D (1737) nvs: nvs_get ap.hidden 1
    D (1747) nvs: nvs_get ap.max.conn 1
    D (1747) nvs: nvs_get bcn.interval 2
    D (1757) nvs: nvs_get ap.phym 1
    D (1757) nvs: nvs_get ap.phybw 1
    D (1757) nvs: nvs_get ap.sndchan 1
    D (1767) nvs: nvs_get lorate 1
    D (1767) nvs: nvs_set_blob sta.mac 6
    D (1767) nvs: nvs_set_blob ap.mac 6
    I (1777) wifi: wifi firmware version: af21fdf
    I (1777) wifi: config NVS flash: enabled
    I (1777) wifi: config nano formating: disabled
    I (1787) wifi: Init dynamic tx buffer num: 32
    I (1787) wifi: Init data frame dynamic rx buffer num: 32
    I (1797) wifi: Init management frame dynamic rx buffer num: 32
    I (1797) wifi: Init management short buffer num: 32
    I (1807) wifi: Init static rx buffer size: 1600
    I (1807) wifi: Init static rx buffer num: 10
    I (1807) wifi: Init dynamic rx buffer num: 32
