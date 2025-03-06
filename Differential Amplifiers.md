# Experiment 3
<br> **Designing of an Differential Amplifier Circuit**</br>
## Aim
Design and analyze the MOS differential amplifier circuit for the given specifications:
- Supply voltage (V<sub>DD</sub>) = 2.5V
- Power Consumption (P) <= 3mW
- Input Common Mode Voltage (V<sub>icm</sub>) = 1.3V
- Output Differential Common Mode Voltage (V<sub>ocm</sub>) = 1.4V
- Node voltage (V<sub>p</sub>) = 0.5V
- Threshold Voltage (V<sub>th</sub>) = 0.36V  (from lib file)
  
Analysis:
- DC operating point :- we need to design Resistor values and set the exact Q point or an operating point.
- Transisent Analysis: we need to verify the output and calculate the differential mode gain (A<sub>dm</sub>). we need to show the max output swing with calculations.
- AC Analysis: we need to analyse the 3dB bandwidth.

## Theroy
<p>The elegant concept of differential signals and amplifiers was invented in the 1940s
 and first utilized in vacuum-tube circuits.</p>
<p>A Differential Amplifier is an funadamental electronic circuit designed to amplify the difference between the two input signals while rejecting an Common-Mode signals that are present on the both input signals. This characteristic makes it highly effective in applications requiring noise reduction. The Differential amplifier typically consists of a pair of transistors configured in a symmetrical manner,allowing it to obtain high common-mode rejection ratio(CMMR).Key performance parameters include gain,input impedance,output impedance and bandwidth.Its ability to amplify differential signals and suppress common-mode noise, the differential amplifier plays a critical role in improving the accuracy and reliability of analog electronic systems. </p>

## Circuit 1 
- with Rss resistane.
![Image](https://github.com/user-attachments/assets/c5e56122-7782-4d77-84b5-f03c9e4f847d)
Design of an circuit
- Assume M1 and M2 are perfectly identical
- Vicm1 = Vicm2 = Vicm
- R<sub>D1</sub> = R<sub>D2</sub> = R<sub>D</sub>
- I<sub>D1</sub> = I<sub>D2</sub> = I<sub>ss</sub>/2
- V<sub>GS1</sub> = V<sub>GS2</sub> =V<sub>GS</sub>
- V<sub>ocm1</sub> = V<sub>ocm2</sub> = V<sub>ocm</sub> = 1.4V
- Vicm = Vp + V<sub>GS</sub>
  - 1.3 = 0.5 + V<sub>GS</sub>
  - 1.3-0.5 = V<sub>GS</sub>
- <table>
  <td>V<sub>GS</sub> = 0.8V</td>
  </table>
  we can conclude that V<sub>GS</sub> >= V<sub>th</sub> , M1 and M2 are in ON state 
 - Given P = 3mW we can calucalate I<sub>ss</sub>
  - I<sub>ss</sub> = P/V<sub>DD</sub>
    - I<sub>ss</sub> = 3mW/2.5V
    - I<sub>ss</sub> = 1.2mA
    - we known that I<sub>D</sub> = I<sub>ss</sub>/2 = 1.2mA/2
     <table>
      <td>I<sub>D</sub> = 0.6mA</td>
      </table>
- Rss = Vp/I<sub>ss</sub> = 0.5/1.2m
    <table>
     <td>R<sub>ss</sub> = 0.416K</td>
     </table>
- V<sub>ocm</sub> = V<sub>DD</sub> - I<sub>D</sub>*R<sub>D</sub>
- R<sub>D</sub> = (V<sub>DD</sub> - V<sub>ocm</sub>)/I<sub>D</sub>
  - R<sub>D</sub> = (2.5 - 1.4)/0.6m
   <table>
    <td>R<sub>D</sub> = 1.833K</td>
    </table>
- we can conclude V<sub>ocm</sub> >= V<sub>GS</sub> - V<sub>th</sub>
   - V<sub>ocm</sub> = 0.8 - 0.36
     <table>
       <td>V<sub>ocm</sub> >= 0.44V</td>
     </table>
     therefore M1 and M2 are in saturation region 
- simulation
  
 ![Image](https://github.com/user-attachments/assets/37c92734-d5be-43e2-b53c-eb0a679c2308)
## when the V<sub>icm</sub> level is 500mV lesser than the given value(1.3V)
- V<sub>icm</sub> will be 1.3 - 0.5 = 0.8V
  
 ![Image](https://github.com/user-attachments/assets/96e979e6-d505-410b-ae62-f302f748309d)

- We can conculde that when we decrease the V<sub>icm</sub> then 
    -  the **V<sub>ocm</sub>** will increase.
    -  the **I<sub>D</sub>** will decrease.
    -  the **A<sub>v</sub>** will decrease.
    -  the total current **I<sub>ss</sub>** will decrease.
    -  the nodal voltage **Vp** will decrease.
## when the V<sub>icm</sub> level is 500mV greater than the given value(1.3V)
- V<sub>icm</sub> will be 1.3 + 0.5 = 1.8V

 ![Image](https://github.com/user-attachments/assets/dbb2a5e4-2265-4180-b443-ade10b6fff96)

  - We can conculde that when we increase the V<sub>icm</sub> then
      -  the **V<sub>ocm</sub>** will decrease.
      -  the **I<sub>D</sub>** will increase.
      -  the **A<sub>v</sub>** will increase.
      -  the total current **I<sub>ss</sub>** will increase.
      -  the nodal voltage **Vp** will increase.
   <table>
     <tr>
        <td>V<sub>icm</sub> (V)</td>
        <td>V<sub>ocm</sub> (V)</td>
        <td>I<sub>D</sub> (A)</td>
        <td>V<sub>p</sub> (V)</td>
        <td>I<sub>ss</sub> (A)</td>
        <td>A<sub>v</sub></td>
     </tr>
     <tr>
       <td>0.8</td>
       <td></td>
     </tr>
  </table>
  - Transisent Analysis:
  - A<sub>v</sub> = -g<sub>m</sub>*R<sub>D</sub>
    - g<sub>gm</sub> = (2*I<sub>D</sub>)/(V<sub>GS</sub> - V<sub>th</sub> )
    - g<sub>gm</sub> = (2*0.6m)/(0.8-0.36)
    - g<sub>gm</sub> = 2.77m
  - A<sub>v</sub> = - 2.7m * 1.83K
    <table>
      <td>A<sub>v</sub> = - 4.99V/V</td>
    </table>
- simulation

  ![Image](https://github.com/user-attachments/assets/55c626a6-cf20-4b9e-a95a-81157eebd55e)
- from simulation the differential gain will be A<sub>vdm</sub> = (V<sub>ocm1</sub> - V<sub>ocm2</sub> )/(V<sub>icm1</sub> - V<sub>icm2</sub>)
   -  A<sub>vdm</sub> = 452.87mV/100mV
     <table>
     <td>A<sub>vdm</sub> = 4.528V/V</td>
     </table>
 - To find Max and Min Swing 
     - V<sub>icm min</sub> = V<sub>th</sub> + Vp
     - V<sub>icm min</sub> = 0.36 + 0.5
     - V<sub>icm min</sub> = 0.86V
     - V<sub>icm max</sub> = V<sub>DD</sub> - (I<sub>D</sub>*R<sub>D</sub>) + V<sub>th</sub>
     - V<sub>icm max</sub> = 2.5 - (0.6m*1.833k) + 0.36
     - V<sub>icm max</sub> = 1.7602V
     - V<sub>icm</sub>max swing = (0.86 + 1.7602)/2
       <table>
         <td>V<sub>icm</sub>max swing = 1.310V</td>
       </table>
    - V<sub>ocm min</sub> = V<sub>ov1</sub> + v<sub>p</sub>
    - V<sub>ocm min</sub> = 0.8 - 0.36 + 0.5
    - V<sub>ocm min</sub> = 0.94V
    - V<sub>ocm max</sub> = V<sub>DD</sub> - I<sub>D</sub>*R<sub>D</sub>
    - V<sub>ocm max</sub> = 2.5 - (0.6m*1.83K)
    - V<sub>ocm max</sub> = 1.4V
    - V<sub>ocm</sub>maxswing = (0.94 + 1.4)/2
      <table>
        <td>V<sub>ocm</sub>maxswing = 1.17V</td>
      </table>
 - simulation
      
      ![Image](https://github.com/user-attachments/assets/5019afc3-c582-403e-b1ae-2bf3fe4e3e52)
   - we can verify by the graph
   - the wave is starting from 1.325V and reached till 2.498V
   - therefore 2.948 - 1.325 = 1.173V which is equal to the calculated value V<sub>ocm</sub>maxswing.
- AC Analysis:
- we got A<sub>v</sub> = -4.99V/V
- A<sub>vdB</sub> = 20log(A<sub>v</sub>)
- A<sub>vdB</sub> = 20log(4.99)
  <table>
    <td>A<sub>vdB</sub> = 13.96 dB</td>
  </table>
- we need to calculate 3dB gain
- 3dB gain = A<sub>vdB</sub> - 3dB
- 3dB gain = 13.96 - 3
  <table>
    <td>3dB gain = 10.96 ~ 11dB</td>
  </table>
- Simulation
  
 ![Image](https://github.com/user-attachments/assets/2cc56e65-1255-42f5-8fa3-2e9352151be6)
- From the graph the gain is 13.180 dB
- The 3 dB bandwidth will be 19.433 GHz 
## Analysis
- When we change the magnitude of V<sub>icm1</sub> = V<sub>icm2</sub> = V<sub>icm</sub>
  <table>
    <td>V<sub>icm</sub> (V)</td>
    <td>V<sub>ocm</sub> (V)</td>
    <td>I<sub>D</sub> (A)</td>
    <td>V<sub>p</sub> (V)</td>
    <td>I<sub>ss</sub> (A)</td>
  </table>

    
