# WS2811F

`WorldSemi WS2811F`

![WS2811F.jpg](./WS2811F.jpg)


```
WS2811F
100006
```


### Description

The WS2811 is 3 output channels special for LED driver circuit. Its internal includes intelligent digital port data latch and signal reshaping amplification drive circuit. Also include a precision internal oscillator and a 12V voltage programmable constant current output drive. In the purpose of reduce power supply ripple, the 3 output channels designed to delay turn-on function.

IC use single NZR communication mode. After the chip power-on reset, the DIN port receive data from controller, the first IC collect initial 24bit data then sent to the internal data latch, the other data which reshaping by the internal signal reshaping amplification circuit sent to the next cascade IC through the DO port. After transmission for each chip, thesignal to reduce 24bit. IC adopt auto reshaping transmit technology, making the chip cascade number is not limited thesignal transmission, only depend on the speed of signal transmission.

The data latch of IC depend on the received 24bit data produce different duty ratio signal at OUTR, OUTG, OUTB port. All chip synchronous send the received data to each segment when the DIN port input a reset signal. It will receive new data again After the reset signal finished. Before a new reset signal received, the control signal of OUTR ,OUTG,OUTB port unchanged. IC sent PWM data that received justly to OUTR, OUTG, OUTB port, after receive a low voltage reset signal the time retain over 280μs.

### Artifacts

* [Datasheet](./artifacts/C5446692.pdf)


### Sources

* [http://www.world-semi.com/ws2811-family/189.html](http://www.world-semi.com/ws2811-family/189.html)
