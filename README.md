# soundLocalizationHardware

testbench boards for piezo hydrophone signal conditioning hardware


![20240310_190803_HDR_1](https://github.com/PetervandenDoel/soundLocalizationHardware/assets/73015873/dfb8413c-6320-42be-a106-c4a3e5a5b15c)



This design consists of a highly configurable four stage amplifier connected to a highly configurable 4 stage filter IC LTC1562.

Preamp design

A low noise, low offset, low bias current quad opamp was chosen and routing was done to allow the user to easily connect in either a charge amplifier or inverting amplifier configuration on the cascaded stages. It is possible to achieve non inverting or buffer configurations, but this would require strapping some terminals together with wires in ways not achieved by the default PCB routing. This image in Microsoft paint demonstrates how to do this.

![image](https://github.com/PetervandenDoel/soundLocalizationHardware/assets/73015873/71ca34d7-5305-4f47-9256-ee673b2531e9)


![image](https://github.com/PetervandenDoel/soundLocalizationHardware/assets/73015873/0e4bf928-a318-40b9-a115-a6704e7e4156)



In hindsight, a four stage amplifier may have been unnecessary but it was chosen to allow for multiple preamplifier stages or buffering. When in use the amplifier's final stage ended up being manually soldered to the input terminal of the LTC 1562. 
