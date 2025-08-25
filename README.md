# RC Low-Pass Filter and -3 dB Frequency

## Overview
This is a small personal project where I modelled a simple RC low-pass filter in LTSpice to find its cutoff (-3 dB) frequency. The aim was to verify the expected behaviour of the filter and compare the measured cutoff from an AC sweep with the theoretical value.

## Parts and values
- R1 = 100 ohm  
- C1 = 4.7 nF  
- Input source: V1 (AC amplitude = 1)

## Circuit diagram
<img width="1920" height="918" alt="Main Circuit" src="https://github.com/user-attachments/assets/e1839066-f2f4-4b4e-972d-4dc73096e05e" />

## Simulation setup
- Simulator: LTSpice  
- Analysis type: AC analysis (decade sweep)  
- Frequency range: 1 Hz to 1 MHz  
- Points per decade: 20

## How I ran it
1. Built the circuit in LTSpice with the components listed above.  
2. Set the AC source amplitude to 1 so the magnitude plot directly represents the transfer function.  
3. Ran an AC sweep from 1 Hz to 1 MHz with 20 points/decade.  
4. Zoomed in around the magnitude drop to find the -3 dB point more precisely.

## Observations and results
<img width="1920" height="1080" alt="Initial -3dB" src="https://github.com/user-attachments/assets/d16286dc-3ba8-482e-8286-9e34d84eaf82" />

- Initial rough reading for the -3 dB point: approximately 339.13 kHz.
<img width="1920" height="1080" alt="Zoomed_In -3dB" src="https://github.com/user-attachments/assets/c652ff64-d3ae-4ec4-bb96-ce3944aff74d" />
<img width="1920" height="1080" alt="Accurate_Zoomed_In -3dB" src="https://github.com/user-attachments/assets/75ff6ec5-cebf-4ca2-b372-198da1f1c5af" />

- After zooming in and finding the closest point on the plot: -3.0007225 dB at 337.32842 kHz.  
- These results are consistent with the expected behaviour of an RC low-pass filter and closely match theoretical predictions.

## Theoretical note (short)
For a simple RC low-pass filter the cutoff frequency (fc) is given by:
fc = 1 / (2 * pi * R * C)

With R = 100 ohm and C = 4.7 nF, the theoretical cutoff is in the same range as the measured value above.

## Conclusion
The RC low-pass filter behaves as expected. The measured -3 dB frequency (around 337 kHz) matches the theoretical value closely, confirming that the filter attenuates higher frequencies while passing lower frequencies with minimal attenuation.

## Files included
- All circuit files are uploaded in the folder named: Circuit Files  
- All images and simulation screenshots are uploaded in the folder named: Images
- Also possible next steps: try different resistor or capacitor values, add load resistance and observe its effect, or sweep component tolerances to see how fc shifts.

