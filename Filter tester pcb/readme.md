This circuit board was designed to test out two identical 4th order filters on the same PCB to characterize the difference in their phase response. This board has not been tested yet and for the time being phase response characterization can be done fine on the through hole boards.

Two 0402 SMD pads are placed at every node where a resistor or capacitor needs to be placed for configuring the filter. the reason why two sets of pads were routed is because standard resistor and capacitor values on their own do not allow for a good bessel Butterworth or chebyshev response at a sufficently customizable frequency. I found that I was able to get good Butterworth Chevy chev and vessel responses in simulations using standard resistor and capacitor values provide that I allowed myself to put two of them in series on each terminal. 



![image](https://github.com/PetervandenDoel/soundLocalizationHardware/assets/73015873/8ef9e591-8ed7-4e35-b8b7-222cc4af3120)
The right combination of standard values can be acquired from an online calculator



![image](https://github.com/PetervandenDoel/soundLocalizationHardware/assets/73015873/32354a91-424d-44c8-be75-09c4fc334360)

![image](https://github.com/PetervandenDoel/soundLocalizationHardware/assets/73015873/b8d1266c-7368-4753-98f4-186ca92bc882)
