# miZy-uboot

[![Build Status](https://travis-ci.com/hyphop/miZy-uboot.svg?branch=master)](https://travis-ci.com/hyphop/miZy-uboot)

Advanced u-boot (for sunxi Orange Pi Zero, another sunxi boards maybe work too ), ready for full load linux from spi-flash, i2c display, FEL mode, and many other improvement 

Its just a part of miZy project, and same as other our parts can standalone used

## Features

* boot from h2+ h3 sunxi boards
* Orange Pi Zero h2+ tested 
* Orange Pi Zero Plus2 h3 tested 
* Orange Pi R1 h2+ tested 
* boot from spi-flash and next **full load linux from spi-flash** is ready via new added [spiread] cmd
* ready for **fast** uboot & full linux **load**, with boot-time about **0.5 & 4-8 sec** (MMC-SPI), from power-on time
* **4x increase SPI-flash reading speed** in SPL-loader and UBOOT ( spi work on **24Mhz** freq now )
* **i2c** available on TWI0 (PA11 PA12)
* **splash screen** on **ssd1306** i2c OLED 128x64 display TWI0 connected
* ready for uboot splash screen customization
* can fix (set or disable) **FEL mode** direct from uboot shell (write or clear FEL-loader on mmc)
* support any **LZMA LZO GZIP** uboot packed images, and directly from uboot shell cmds
* accept uboot images with bad crc 
* fast advanced configuration for build-in uboot environment, without recompilation
* ready for next **USB loading** from any 3 usb ports
* new improved building system full automated, speed + size optimized 
* **easy** write new **patches** with find_changes script
* led indication and splash for boot process
* many other small fix & adds

[spiread]: https://github.com/hyphop/miZy-uboot/blob/master/docs/spiread.md

## SPI NOTE

by default device can not have SPI flash or have only 2M bytes (mx25l1606e its enough for uboot only),
needed re/install SPI flash to 4M or 8M or 16M bytes if u need  full load linux from spi-flash. For example 
we have tested on W25q128 spi flash, and this worked well!

## Get Source, Prepare, Build & Clear - need only 10-30 sec for build uboot

    cd /tmp
    mkdir zero_builder
    cd  zero_builder

    git clone https://github.com/hyphop/miZy-uboot
    cd miZy-uboot

    ./uboot_prepare
    ./uboot_build

!note: if have permissions problems with modprobe|mount overlay try `sudo bash` before `./uboot_prepare` ...


<!--building time test
    echo START; mkdir /tmp/zero_builder; cd /tmp/zero_builder; date ; git clone https://github.com/hyphop/miZy-uboot; cd miZy-uboot; ./uboot_prepare; ./uboot_build; date; echo "END"
-->

if everything is ok, compilled uboot must be there **./uboot-mizy.bin**, and ready for usage!
now we can clear building data.

    ./uboot_clear_all

## Easy make - by one-line command

    wget http://raw.githubusercontent.com/hyphop/miZy-uboot/master/make_it_easy -O- | sh -

## Output

* u-boot-sunxi-with-spl.bin -> ./uboot-mizy/u-boot-sunxi-with-spl.bin
* uboot-mizy.bin -> **../bin/uboot/uboot-mizy.bin**
    
## Deps and cross compilation

* dtc v1.4.3 (flex + bison)
* toolchain-arm_cortex-a9+neon_gcc-5.3.0_musl-1.1.15_eabi

its easy and automated by scripts!

## binary downloads

* https://github.com/hyphop/miZy-uboot/releases/download/v0.1-beta/uboot-mizy.bin

## miZy 
 
miZy - open source minimalistic tiny fast embedded Linux system, (for sunxi Orange Pi Zero, another sunxi boards maybe work too )

## NOTES

some source code parts in low quality ( sorry but I'm new to uboot ), some parts not annotated not documented, we stay in active develop now! wellcome to join us improve & tidy this code.

## LINKS

- [https://github.com/hyphop/miZy-linux-kernel](https://github.com/hyphop/miZy-linux-kernel)
- [https://github.com/hyphop/miZy-builder](https://github.com/hyphop/miZy-builder)
- [https://github.com/hyphop/miZy-uboot](https://github.com/hyphop/miZy-uboot)
- [https://hyphop.github.io/mizy/](https://hyphop.github.io/mizy/) - miZy - Tiny fast embeded linux

## ;)

![miZy](pics/miZy.logo.bw128x64x2.png)
