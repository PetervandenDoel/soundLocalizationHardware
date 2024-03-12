# soundLocalizationHardware

testbench boards for piezo hydrophone signal conditioning hardware. It is quite lucky that JLC gives five circuit boards in each order and we will be using 5 hydrophones for our localization algorithm


![20240310_190803_HDR_1](https://github.com/PetervandenDoel/soundLocalizationHardware/assets/73015873/dfb8413c-6320-42be-a106-c4a3e5a5b15c)



![image](https://github.com/PetervandenDoel/soundLocalizationHardware/assets/73015873/37b3d958-6139-4155-a68c-3f8d2bf308d6)

![image](https://github.com/PetervandenDoel/soundLocalizationHardware/assets/73015873/195ba782-8f36-4b33-aea0-edb79cd72258)


This design consists of a highly configurable four stage amplifier connected to a highly configurable 4 stage filter IC LTC1562.

# Preamp design

A low noise, low offset, low bias current quad opamp was chosen and routing was done to allow the user to easily connect in either a charge amplifier or inverting amplifier configuration on the cascaded stages. It is possible to achieve non inverting or buffer configurations, but this would require strapping some terminals together with wires in ways not achieved by the default PCB routing. This image in Microsoft paint demonstrates how to do this.

![image](https://github.com/PetervandenDoel/soundLocalizationHardware/assets/73015873/71ca34d7-5305-4f47-9256-ee673b2531e9)


![image](https://github.com/PetervandenDoel/soundLocalizationHardware/assets/73015873/0e4bf928-a318-40b9-a115-a6704e7e4156)



In hindsight, a four stage amplifier may have been unnecessary but it was chosen to allow for multiple preamplifier stages or buffering. When in use the amplifier's final stage ended up being manually soldered to the input terminal of the LTC 1562. 



# Filter design

the LTC 1562 contains 4 configurable second order filter blocks. Depending on the use of resistors and capacitors and which one is routed as the output one can achieve low pass high pass or bandpass configurations. On all the circuit boards here, the filter IC is routed to only allow for low pass or bandpass(Terminal 2 of each stage is routed as the output). This was a challenging component to solder by hand with no stencil but it was done.

Unfortunately, we will be transitioning away from this design because the price of the LTC 1562 increased from $20 to $45.00 in the past few months and we need 5 of them. We plan to transition towards using it the LTC 1563-2 which only allows for lowpass and bandpass stages, and require some additional buffering on the output in order to drive any load above a few picofarads(EG oscilloscope probes on 1X as opposed to 10X setting), but only costs $20.


# Aesthetics and user friendlyness

Silk screens were copied between the top and bottom of the board which ended up being very useful when soldering and de-soldering. The most important nodes that jumper wires were frequently soldered into to probe were labeled with arrows or other things pointing to those nodes to make them easy to see. Since these circuit boards serve as test benches for different signal conditioning hardware designs, it is essential that components can be soldered and desoldered from the circuit board easily and that things are clearly labeled so that one doesn't have to open Altium designer just to use the circuit boards.



the circuit boards were made in funny shapes just to keep it fresh and give us a chance to play around with board outlines. Due to there being components on the front and back of the circuit board and a lot of jumper wires that ended up being soldered in, the circuit boards that were easiest to solder were the ones that had flat sides and fit well in a vice, the fish circuit board became a little bit annoying to suspend in a vice. 




# Power considerations 

In order to allow maximum dynamic range and for ease of design and use, dual +-5 Volt supplies are used. The large capacitors on the input of the power are used to decouple the circuit from the inductance of long windy wires that we inevitably ended up using to connect the circuit boards. Very small 0402 decoupling capacitors were used on all the IC's. They were soldered by hand which is about as much fun as it sounds like, future designs will probably use 0805 instead. 


# Saftey considerations for the sensitive LTC1562

The LTC 1562 datasheet strongly recommends against saturating the output stage of the filter in particular. If you feed it the signal with large amounts of noise but it filters it down to a signal below the power rails that's fine, but if your signal still sits above the power rails after filtration, then it runs a risk of damaging the IC. The LTC 1563-2 also has this problem. To fix it in future designs while still allowing us to have high gain and potentially get very close to the sound source, the preamplifier stages will be powered with +-4.5 Volt rails to ensure that they clip the signal before it reaches the LTC 156 3-2 which will be driven with +-5 volt rails. So long as the filter doesn't provide amplification, there will be no risk of saturation causing any damage to the 1563-2.

Reading forum posts about sudden voltages due to thermal stresses on piezo hydrophones being dipped in water, TVS diodes were used on the inputs of the amplifier and filter. These were also 0402. 

Due to exposed stitching vias on the non fish shaped through hole PCB, one of the terminals of the LTC 1562 got shorted to ground and the IC was destroyed, thankfully we have two. A pretty silly mistake considering that the stitching did nothing for signal integrity and was essentially just aesthetics. 











