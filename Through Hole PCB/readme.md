This is a through hole version of the design which is supposed to be optimized for maximum configurability. All parts can be easily hotswapped due to them being connected through hole.

Its a 4 layer board with signal gnd gnd signal stackup but signal integrity is not a terrible concern because our circuit doesn't operate anywhere above 50 kHz, low ultrasonic.
The fish shaped circuit board doesn't contain ground planes, just copper pour but still performs equally well.

The board size was kept below 10 by 10 centimeters in order to ensure that JLCPCB would give us thier special discount on a 4 layer board.

![image](https://github.com/PetervandenDoel/soundLocalizationHardware/assets/73015873/0d7abd40-2393-4f35-9f31-ad45ba1267e9)

![image](https://github.com/PetervandenDoel/soundLocalizationHardware/assets/73015873/aaebaf4c-d12e-4ef1-a966-5e05e76f6543)



We ended up getting a short to one of the exposed stitching vias, they were simply added for aesthetics but in hindsight they were troublesome

0402 components are incredibly annoying to solder so future designs will have much bigger passive parts
