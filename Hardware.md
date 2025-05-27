## Abstract
This paper presents the design and implementation of a 3-bit Flash Analog-to-Digital Converter (ADC) using discrete hardware components. Flash ADCs are widely recognized for their high-speed performance, making them suitable for applications requiring rapid data conversion. The proposed 3-bit architecture employs seven comparators, a precision resistor ladder network for reference voltages, and a digital encoder to produce a 3-bit binary output from an analog input. The hardware prototype was developed and tested to verify functionality.  This work demonstrates the feasibility of implementing compact and efficient Flash ADCs in practical systems where high-speed analog signal digitization is essential.
## Instruduction
Analog-to-Digital Converters (ADCs) are pivotal in bridging the analog physical world with the digital processing domain. Flash ADCs are the fastest among the various ADC architectures due to their parallel comparator design, enabling real-time signal conversion with minimal latency. This speed makes them indispensable in applications such as digital oscilloscopes, radar systems, high-speed data acquisition, and modern communication systems.
Flash ADCs provide an excellent case study for applying analog principles such as voltage division, comparator design using op-amps, and logic-level interfacing. This project presents the design and implementation of a 3-bit Flash ADC using discrete analog components. A resistor ladder network creates precise reference voltages, which are fed to seven high-gain comparators constructed using operational amplifiers—key components studied in the LIC subject. The comparator outputs are then processed through a priority encoder to generate a corresponding 3-bit digital output.
This project concentrates on how each analog part of the 3-bit Flash ADC behaves in real hardware. We build and test a resistor-ladder network together with seven comparators and a digital encoder, confirming that the circuit works exactly as classroom theory in Linear Integrated Circuits (LIC) predicts. By turning these core LIC concepts into a working high-speed converter, the work clearly shows how solid analog principles can be transformed into a practical, reliable device, demonstrating both sound academic understanding and hands-on engineering skill.

## 	DESIGN OVERVIEW
**RESISTOR LADDER NETWORK**
The resistor ladder network serves as a precision voltage divider that establishes seven discrete reference voltage levels across eight identical resistors, each valued at 680Ω. This ladder forms the foundation for comparator thresholding, producing evenly spaced voltage steps given by V_step = V_ref / 8. For a 5V reference, this results in voltage levels at approximately 0.625V increments, ranging from 0.625V to 4.375V. These voltages are tapped from the junctions of the resistors and fed directly into the inverting inputs of the comparator array.
 **Comparator Stage**
The heart of the analog comparison is handled by seven LM393 comparators. Each comparator receives a reference voltage from the resistor ladder at its inverting input and the analog input voltage (V_in) at its non-inverting input. When V_in exceeds the respective reference voltage, the comparator output transitions to a logic high. The collective output of the comparators forms a thermometer code, where all comparators below the input voltage threshold output high, and the rest output low. This analog-to-binary transformation stage is essential for ensuring fast and accurate detection of the analog signal’s magnitude.
**Encoder Stage**
The final stage involves converting the thermometer code into a 3-bit binary output. This is achieved using the SN7418 encoder, which prioritizes the highest-order active comparator signal and encodes it into the equivalent binary representation. The encoder simplifies the complex thermometer output into a standard digital form that can be easily interfaced with digital systems for further processing.
This structured, analog-centered design effectively demonstrates the practical implementation of Flash ADC architecture using discrete components. By combining linear resistor-based voltage division, high-gain comparator behavior, and logic-level encoding, the 3-bit Flash ADC exemplifies how analog concepts from LIC theory can be translated into a working, real-time data conversion system
## Block Diagram 
![Image](https://github.com/user-attachments/assets/4227263e-8092-42ae-beb2-7600348c173b)

 - we have assumed the Power budget as 5 mW, V ref = 5V wkt  Iref= Vref / Rtotal
 - Assume that the total ladder should have an impedance of 5kΩ
 - Iref = 1mA , P = 5mW
 - R = Rtotal / 2N
 -  R = 625 Ω (Standard Value R= 680Ω)
  ## Simulation 
![Image](https://github.com/user-attachments/assets/09d92177-bce4-4b91-a0c7-ceda457ec651)

- To generate seven discrete reference voltages (V1 through V7) for the comparator inputs of a 3-bit Flash ADC, a resistor ladder network consisting of eight identical resistors (R) is used. The reference voltage (Vref) is assumed to be 5 V.
- Total resistance across the ladder:
- Rtotal=8×R
- Voltage step across each node:
- Vstep=Vref /8 = 0.625V
- Using this step size, the individual node voltages are calculated as follows: V1=5×7/8=4.375V
- V2=5×6/8=3.75V
-  V3=5×5/8=3.125V
-  V4=5×4/8=2.5V
-  V5=5×3/8=1.875V
-  V 6=5×2/8=1.25V
-  V 7=5/8=0.625V
  These voltages are supplied to the inverting terminals of the LM393 comparators. The analog input signal (Vin) is applied to the non-inverting terminals.
## RESULT
- For a 3-bit Flash ADC, there are 23=82^3 = 823=8 levels and 7 comparators. Assume reference voltages are spaced like this:
- Let Vin = 2.8V Comparator	Reference Voltage (V)	Input > Ref?	Comparator Output
-  C1	0.625	Yes	1
-  C2	1.25	Yes	1
-  C3	1.875	Yes	1
-  C4	2.5	Yes	1
-  C5	3.125	No	0
- C6	3.75	No	0
- C7	4.375	No	0
- C1 to C4 will output 1 because 2.8V > 0.625V, 2.8V > 1.25V, 2.8V > 1.875V and 2.8V > 2.5V.
- C5 to C7 will output 0 because 2.8V < 3.125 is False for C5, and the rest are higher.
- So, the comparator outputs will be: 1 1 1 1 0 0
 Therefore, the digital output would be 100 in binary 
**Truth Table**
  
