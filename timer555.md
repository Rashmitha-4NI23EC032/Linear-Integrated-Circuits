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
  
  
