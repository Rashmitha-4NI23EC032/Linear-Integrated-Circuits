
## Experiment 6
**Design and analyse current mirror circut as ative load in amplifier circuit.**

## Introduction 
 **Current Mirror**
<p>A current mirror circuit is a fundamental building block in analog electronics used to replicate a reference current with high accuracy. It is widely employed in biasing, active loads, and current sources in integrated circuits . The ideal current mirror maintains a stable output current regardless of variations in process, supply voltage, and temperature (PVT).</p>

## Principle of Operation
<p>A basic current mirror consists of two matched  MOSFETs. The first transistor is configured to establish a reference current, and the second transistor mirrors this current by operating under the same conditions. However, practical current mirrors are affected by PVT variations, leading to deviations in the mirrored current.</p>

![Image](https://github.com/user-attachments/assets/61062a24-8243-4a2a-a285-aed0eec6d201)
- Challenges Due to PVT Variations
   - Process Variations (P): Differences in  fabrication leads to mismatches in transistor parameters.
   - Supply Voltage Variations (V): Fluctuations in the power supply alter the transistor’s operating points, making the output current unstable.
   - Temperature Variations (T): Changes in temperature impact MOSFET threshold voltage  causing drift in current.
- How to generate the biased voltage independent of PVT
   - PMOS :- Sourcing Current source
   - NMOS:- Sinking(to ground)
   - we use golden Refernce Current or Bandgap Refernce Circuit.
     
## Classification based on type of moseft used in current mirror circits
- NMOS Currnet Mirroring
   - Uses: N-channel MOSFETs
   - One NMOS transistor is diode-connected  to set the reference current.
   - Faster operation due to high electron mobility.
   
   ![Image](https://github.com/user-attachments/assets/db56a389-6ed7-4f84-b9b5-922d562448a2)
   - Depend on the sizing parameters.
- PMOS current Mirroring
   - Uses: P-channel MOSFETs
   - The reference current is set using a diode-connected PMOS transistor, and another PMOS mirrors it.
    ![Image](https://github.com/user-attachments/assets/8604949f-4987-418b-a266-61bbdc74d823)
## Simulation 
Part A : <p>Design a current mirror circuit which has a gain of AV = -10V/V, power supply of Vdd = 1.8V, and power of P <= 1mW. Find reference current (Iref), output current (Id), and total current (Itotal). Perform DC and AC analysis for mirror ratio 1:1, 1:2.</p>
![Image](https://github.com/user-attachments/assets/4fcd86ec-967b-4d96-98ed-6e4da85dbf7c)
  -  The MOSFET should be in saturation region 
<table>
<td>V1>V<sub>th</sub></td>
</table>
i.e 0.5>0.366
 
  -  I<sub>taotal</sub>=P/V<sub>dd</sub>
<table>
<td>I<sub>total</sub>=0.55mA</td>
</table>
I<sub>total</sub>=I<sub>ref</sub> + I<sub>p</sub>
I<sub>ref</sub>=I<sub>p</sub>=(I<sub>total</sub>)/2
<table>
<td>I<sub>ref</sub>=I<sub>p</sub>=0.27mA</td>
</table>

![Image](https://github.com/user-attachments/assets/9b97f1b6-8c16-45cb-90f8-ac0348f00216)  ![Image](https://github.com/user-attachments/assets/92dda9af-d6bb-4973-8655-4f7277f4715e)
 <table> 
<tr>
 <th><b>Parameters</b></th>
 <th><b>MOSFET1</b></th>
 <th><b>MOSFET2</b></th>
 <th><b>MOSFET3</b></th>
</tr>
<tr>
    <td>Model</td>
    <td>CMOSP</td>
    <td>CMOSP</td>
    <td>CMOSN</td>
</tr>
<tr>
    <td>Length</td>
    <td>180nm</td>
    <td>180nm</td>
    <td>180nm</td>
</tr>
<tr>
    <td> Width</td>
    <td>70µm</td>
    <td>70µm</td>
    <td>100.0217999um</td>
</tr>
<tr>
    <td>V<sub>th</sub></td>
    <td> -0.507V</td>
    <td> -0.507V</td>
    <td> 0.496V</td>
</tr>
    <tr>
      <td>Current(I)</td>
      <td>  0.27mA </td>
      <td>  0.270211mA </td>
      <td> 0.270211mA </td>
    </tr>
    <tr>
      <td>Supply Voltage</td>
      <td> 1.8V</td>
      <td> 1.8V</td>
      <td> --- </td>
    </tr>
     <tr>
      <td>Biased Voltage</td>
      <td> --- </td>
      <td> --- </td>
      <td> 0.5697V</td>
    </tr>
</table>
