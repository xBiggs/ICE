# BQ40Z80

`Texas Instruments BQ40Z80 2-s to 6-s battery pack manager with Impedance Track™ gas gauging`

![BQ40Z80.jpg](./BQ40Z80.jpg)

```
BQ40Z80
TI 5B8
CIQ4
```

### Description

Firmware: https://www.ti.com/tool/download/SLUC672

Cant download due to export controls here

The BQ40Z80 device is a fully integrated, single-chip option that incorporates patented Impedance Track technology. The BQ40Z80 device provides a range of features for gas gauging, protection, and authentication, supporting 2-series to 6-series cell Li-ion and Li-polymer battery packs.

Using integrated high-performance analog peripherals, the BQ40Z80 device measures and maintains an accurate record of available capacity, voltage, current, temperature, and other critical parameters in Li-ion or Li-polymer batteries. The record is reported to the system host controller over an SMBus v1.1 compatible interface.

Elliptic curve cryptography (ECC) or SHA-1 authentication with secure memory for authentication keys enables identification of genuine battery packs.

The BQ40Z80 device supports TURBO Mode 2.0/Intel Dynamic Battery Power Technology (DBPTv2) by providing the available max power and max current to the host system. The device has eight multifunction pins that can be configured as thermal inputs, ADC inputs, general purpose input/output (GPIO) pins, a presence pin, LED functions, display button input, or other functions. Status and flag registers are mappable to the GPIOs and used as interrupts to the host processor.

The BQ40Z80 device provides software-based 1st- and 2nd-level safety protection against overvoltage, undervoltage, overcurrent, short-circuit current, overload, and overtemperature conditions, as well as other pack-related and cell-related faults. The compact 32-lead QFN package minimizes the cost and size for smart batteries, while providing maximum functionality and safety for battery gauging applications.


### Interfaces

* 2-wire SMBus v1.1


### Artifacts

* [Datasheet](./artifacts/bq40z80.pdf)
* [Technical Reference Manual](./artifacts/sluubt5c.pdf)
* [Firmware](https://www.ti.com/tool/download/SLUC672)


### Sources

* [https://www.ti.com/product/BQ40Z80](https://www.ti.com/product/BQ40Z80)

