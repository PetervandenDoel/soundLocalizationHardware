This circuit board was designed as an alternative to the through hole designs but it did not end up being used. The through hole designs were there to serve as a test bench where parts could be swapped out easily and different designs could be tested and then the surface mount designs would be our final version. However, enough design flaws have been discovered that we will probably just redesign the through hole versions and then only make surface mount versions once we are very confident in our designs.

Thank goodness we did not actually try to assemble these, soldering 0402 resistors and capacitors would have been a nightmare(but doable)

For the surface mount designs 0402 SMD pads are placed at every node where a resistor or capacitor needs to be placed for configuring the filter. the reason why two sets of pads were routed is because standard resistor and capacitor values on their own do not allow for a good Bessel Butterworth or Chebyshev response at a sufficently customizable frequency. I found that I was able to get good Butterworth chebyshev and Bessel responses in simulations using standard resistor and capacitor values provide that I allowed myself to put two of them in series on each terminal.

![image](https://github.com/PetervandenDoel/soundLocalizationHardware/assets/73015873/190cdb58-fa8e-480b-bf4e-937d2bf105f9)

![image](https://github.com/PetervandenDoel/soundLocalizationHardware/assets/73015873/7475415a-3f9f-41d8-98f4-bae59816b238)
