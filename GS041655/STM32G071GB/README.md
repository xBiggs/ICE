# STM32G071GB

`STMicroelectronics  STM32G071GB Mainstream Arm Cortex-M0+ MCU with 128 Kbytes of Flash memory, 36 Kbytes RAM, 64 MHz CPU, 4x USART, timers, ADC, DAC, comm. I/F, 1.7-3.6V`

![STM32G071GB.jpg](./STM32G071GB.jpg)

```
G071GB
GQ20017
VQCHN2
   604
```


### Description

The STM32G071x8/xB mainstream microcontrollers are based on high-performance Arm® Cortex®-M0+ 32-bit RISC core operating at up to 64 MHz frequency. Offering a high level of integration, they are suitable for a wide range of applications in consumer, industrial and appliance domains and ready for the Internet of Things (IoT) solutions.

The devices incorporate a memory protection unit (MPU), high-speed embedded memories (36 Kbytes of SRAM and up to 128 Kbytes of flash program memory with read protection, write protection, proprietary code protection, and securable area), DMA, an extensive range of system functions, enhanced I/Os, and peripherals. The devices offer standard communication interfaces (two I2Cs, two SPIs / one I2S, one HDMI CEC, and four USARTs), one 12-bit ADC (2.5 MSps) with up to 19 channels, one 12-bit DAC with two channels, two fast comparators, an internal voltage reference buffer, a low-power RTC, an advanced control PWM timer running at up to double the CPU frequency, five general-purpose 16-bit timers with one running at up to double the CPU frequency, a 32-bit general-purpose timer, two basic timers, two low-power 16-bit timers, two watchdog timers, and a SysTick timer. The devices provide a fully integrated USB Type-C Power Delivery controller.

The devices operate within ambient temperatures from -40 to 125°C and with supply voltages from 1.7 V to 3.6 V. Optimized dynamic consumption combined with a comprehensive set of power-saving modes, low-power timers and low-power UART, allows the design of low-power applications.

VBAT direct battery input allows keeping RTC and backup registers powered.

The devices come in packages with 28 to 64 pins. Some packages with low pin count are available in two pinouts, standard and alternative. The devices with the alternative pinout, marked with N suffix, offer an additional UCPD port. They are the best choice for UCPD applications.


### Interfaces

* 2x I2C-bus interfaces supporting Fast-mode Plus (1 Mbit/s) with extra current sink, one supporting SMBus/PMBus and wakeup from Stop mode
* 4x USARTs with master/slave synchronous SPI; two supporting ISO7816 interface, LIN, IrDA capability, auto baud rate detection and wakeup feature
* 1x low-power UART
* 2x SPIs (32 Mbit/s) with 4- to 16-bit programmable bitframe, one multiplexed with I2S interface; four extra SPIs through USARTs
* HDMI CEC interface, wakeup on header
* USB Type-C Power Delivery controller
* 1x JTAG SWD


### Artifacts

* [Datasheet](./artifacts/stm32g071gb.pdf)
* [Self-test Library User Guide](./artifacts/um3083-stm32g0-series-iec-60730-selftest-library-user-guide-stmicroelectronics.pdf)
* [Reference Manual](./artifacts/rm0444-stm32g0x1-advanced-armbased-32bit-mcus-stmicroelectronics.pdf)
* [Programming Manual](./artifacts/pm0223-stm32-cortexm0-mcus-programming-manual-stmicroelectronics.pdf)
* [Errata Sheet](./artifacts/es0418-stm32g071x8xb-device-errata-stmicroelectronics.pdf)


### Sources

* [https://www.st.com/en/microcontrollers-microprocessors/stm32g071gb.html](https://www.st.com/en/microcontrollers-microprocessors/stm32g071gb.html)

