## Monostable multivibrator using 555 timer IC .
## Aim
Generate pulse of width 0.5 ms using input triggers
## Intruducation
A multivibrator is a switching circuit that uses two amplifying stages with positive feedback to generate square waves. It oscillates between HIGH and LOW states and is widely used in digital electronics for timing, data storage, and signal generation. There are three types: astable (free-running), monostable (one-shot), and bistable (flip-flop).

The multivibrators are classified into three categories-
- Astable Multivibrator.
- Monostable Multivibrator.
- Bistable Multivibrator.

**Astable Multivibrator**
- It is also known as a free-running multivibrator.
- It has no stable state, hence the name astable.
- It produces a continuous series of pulses with a predetermined frequency and duty cycle.
- It requires two identical transistors two capacitors, and a few resistors.
- It is commonly used in oscillator circuits, pulse generators, and clock circuits.

  **Monostable Multivibrator**
- Also known as a one-shot multivibrator.
- It has only one stable state.
- It produces a single output pulse of a predetermined width when triggered by an input signal.
- It requires two transistors, two capacitors, and a few resistors.
- It is commonly used in timing circuits, delay circuits, and pulse width modulation circuits.

  **Bistable Multivibrator**
  - Also known as a flip-flop multivibrator.
  - It has two stable states and can remain in either state indefinitely without any input signal.
  - It requires two transistors, two capacitors, and a few resistors.
  - It is commonly used in digital circuits as a memory element, latch, or flip-flop.
  - It is also used in applications where a simple on/off switch is required.
  ## Design a Monostable Multivibrator with 555 Timer Circuit to generate pulse of width 0.5 ms using input triggers.
  **Case1**
  ![Image](https://github.com/user-attachments/assets/2503eef2-c5eb-4726-834d-58a9636f07dc)

  **Case2**
![Image](https://github.com/user-attachments/assets/941f5eb9-e864-4bd2-802c-60faf93ffde3)

**Case3**

![Image](https://github.com/user-attachments/assets/7e1aa86c-16dd-4c00-adff-45d5da2802c9)

  A monostable multivibrator generates a single, fixed-duration output pulse in response to a trigger, regardless of the trigger’s duration. The output pulse width is set by the circuit’s resistor-capacitor (RC) time constant. It responds only to the first valid trigger and ignores additional triggers during the output pulse period. This makes it ideal for timing applications, pulse shaping, and debouncing.

  ## Astable multivibrator and monostable multivibrator using 555 timer IC
  **Circuit Diagram**
  ![Image](https://github.com/user-attachments/assets/6dfda79b-c236-429f-bc2c-40f6b9bad91f)
  ## Calculation 
  ![Image](https://github.com/user-attachments/assets/cec77012-85ce-417d-bb66-640ed8e89629)
![Image](https://github.com/user-attachments/assets/1926d939-3b3b-4d6d-b7a7-3e9e763d83ea)

**Case1**
  ![Image](https://github.com/user-attachments/assets/43b9ea37-5d91-4512-822b-7d29324595fe)
  
**Case2**
![Image](https://github.com/user-attachments/assets/54b0b36b-b937-4d22-b4b3-fb1c4cf217b5)

**Case 3**
the ton<toff which is not possible in astable Multivibrator , thus we can use an inverter to invert the pulse generated.
## Inference 
Controlling ON and OFF Times Isn't Always Straightforward We saw that changing resistor and capacitor values lets us control how long the signal stays ON and OFF. But it’s not always possible to get any values we want with the basic 555 timer setup.

The 555 Timer Has Its Limits In some cases (like when OFF time needs to be longer than ON), the normal 555 astable circuit can’t give us the result directly. That’s why in Case 3, we had to flip the signal using an inverter.

Inverters Can Help Us Get the Waveform We Want By adding a simple NOT gate (built using a transistor), we were able to reverse the timing — this gave us more flexibility in generating the waveform we needed.

Very Short Pulses Need Precise Components In Case 2, we worked with very fast pulses (just fractions of a millisecond). To do that, we needed low resistor and capacitor values — which also showed us the importance of accuracy and how component selection affects timing.

We Can Detect Edges Using a Differentiator A differentiator circuit helped us catch the exact moment the signal goes from LOW to HIGH. This is useful when we only want to react to changes, not the full pulse.

Monostable 555 Gives Clean, Consistent Pulses Finally, when we triggered a monostable 555 with those edges, we got clean, uniform pulses every time. This is super helpful when we need a reliable output regardless of input width.

| **Case** | **Configuration** | **Observation** |
|----------|-------------------|----------------------|
| **Case 1**<br>(ON = 0.2 ms, OFF = 0.3 ms) | Direct astable 555 output | Basic control of ON/OFF time using R1, R2, and C values works well within certain timing ranges. |
| **Case 2**<br>(ON = 0.1 ms, OFF = 0.05 ms) | High-speed pulse using small R and C | Fast switching is possible but requires precise low-value components. Useful for short pulse generation. |
| **Case 3**<br>(ON = 0.3 ms, OFF = 0.4 ms)<br>with inverter | Inverter used after 555 output | Shows how logical inversion helps overcome 555 timer’s limitations, allowing ON < OFF timing. |
## Simulation in Virtual Lab Astable Multivibrator

