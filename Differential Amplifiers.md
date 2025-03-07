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
        <td>I<sub>D</sub> (mA)</td>
        <td>V<sub>p</sub> (V)</td>
        <td>I<sub>ss</sub> (mA)</td>
        <td>A<sub>v</sub> (V/V)</td>
     </tr>
     <tr>
       <td>0.8</td>
       <td>2.12</td>
       <td>0.207</td>
       <td>0.172</td>
       <td>0.41443</td>
       <td>4.069</td>
     </tr>
     <tr>
       <td>1.3</td>
       <td>1.4</td>
       <td>0.6</td>
       <td>0.5</td>
       <td>1.2</td>
       <td>5</td>
     </tr>
     <tr>
       <td>1.8</td>
       <td>0.894</td>
       <td>0.875</td>
       <td>0.728</td>
       <td>1.751</td>
       <td>2.799</td>
     </tr>
  </table>
  
- **Transisent Analysis:**
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
  
**Range of an V<sub>icm</sub>**
  <table>
    <td>V<sub>GS1</sub> + Vp <= V<sub>icm</sub> <= min(V<sub>DD</sub> - (I<sub>D</sub>*R<sub>D</sub>) + V<sub>th</sub> , V<sub>DD</sub>(when one mosfet is off))</td>
  </table>
      
- **AC Analysis:**
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
## Circuit 2 
- Resistance is replaced by the constant current source
  ![Image](https://github.com/user-attachments/assets/3c3adc1b-daeb-4c36-b447-1d6a2177e7bf)
  - The constant current source ideally it has infinte resistance.
  - For same designed values design the circuit.
**DC Oprating point**
![Image](https://github.com/user-attachments/assets/3916ab46-888e-4900-a91a-4684ad38d030)
**Transient Analysis**
- Do the same procedure done for circuit 1
 ![Image](https://github.com/user-attachments/assets/1f98b790-6d74-4352-bf7c-d5bfce50bd0e)
- A<sub>vdm</sub> = 452.87mV/100mV
     <table>
     <td>A<sub>vdm</sub> = 4.528V/V</td>
     </table>
- Do the same procedure for finding out the Max and Min swing.
  ![Image](https://github.com/user-attachments/assets/e61d9c1c-845d-4525-9347-07a08ca5fd86)
  -  the wave is starting from 1.325V and reached till 2.498V
 - therefore 2.948 - 1.325 = 1.173V which is equal to the calculated value V<sub>ocm</sub>maxswing.
   **AC Analysis**
   -  Do the same procedure done for circuit 1
     ![Image](https://github.com/user-attachments/assets/a005e315-1a63-446f-893b-28483de75615)
  -  From the graph the gain is 13.180 dB
  - The 3 dB bandwidth will be 19.433 GHz
## Circuit 3
- Resistance is replaced by the NMOS
- In this circuit we need to desing the Basing Voltage V<sub>b</sub>.
- For MOSFET 3 to operate in the saturation region.
   - V<sub>GD</sub> <= V<sub>th</sub>
   - V<sub>G</sub> - V<sub>D</sub> = V<sub>th</sub>
   - V<sub>b</sub> = V<sub>th</sub> + V<sub>p</sub>
   - V<sub>b</sub> = 0.366 + 0.5
     <table>
      <td>V<sub>b</sub> = 0.866V </td>
    </table> 
    
    ![Image](https://github.com/user-attachments/assets/5219edf7-0883-43ff-bf56-f508029dac0d)
  - Therefore we can conculde V<sub>GD</sub> <= V<sub>th</sub> it operates in the saturation region.
  - V<sub>GS</sub> > V<sub>th</sub> (On state condition)
  - V<sub>b</sub> > V<sub>th</sub> (V<sub>s</sub> = 0V)
     And all the parameters will be same in the design.
      
    ![Image](https://github.com/user-attachments/assets/da280c0d-d08e-413e-a4b6-2a0a39b88abf)
  **Transient Analysis**
  **Range of an V<sub>icm</sub>**
  <table>
    <td>V<sub>GS1</sub> + V<sub>ov3</sub> <= V<sub>icm</sub> <= min(V<sub>DD</sub> - (I<sub>D</sub>*R<sub>D</sub>) + V<sub>th</sub> , V<sub>DD</sub>(when one mosfet is off))</td>
  </table>
 - V<sub>icm</sub> min = V<sub>GS1</sub> + V<sub>ov3</sub> 
  - V<sub>icm</sub> min = 0.8 + 0.574
  - V<sub>icm</sub> min = 1.374V
 - V<sub>icm</sub> max = (V<sub>DD</sub> - (I<sub>D</sub>*R<sub>D</sub>) + V<sub>th</sub>
   - V<sub>icm</sub> max = (2.5 - (0.6*1.83) + 0.366
   - V<sub>icm</sub> max = 1.768V
- Therefore <table>
               <td> 1.374V <= V<sub>icm</sub> <= 1.768V </td>
               </table> is the range for V<sub>icm</sub>
  - when apply a max swing = (0.94 + 1.768)/2 = 1.35V (for 50mv)
  ![Image](https://github.com/user-attachments/assets/343f67ae-fbcc-4eb3-bbb4-2364e5d0c44c)
               
 **when V<sub>icm</sub> < 0.94V**
 ![Image](https://github.com/user-attachments/assets/a0e09b35-2d1f-4462-bae4-f44d9b4eb941)
   - In this simulation the amplitude is 50mV but aslo we won't get proper symmetrical wave.
 - **When V<sub>icm</sub> > 1.768V**
 ![Image](https://github.com/user-attachments/assets/cc79cfae-4527-4679-abc4-f772b3608c85)
  - We can conclude that when we apply signals greater than the 1.768V the signals will get distroted.
- Therefore first we find out the range of the V<sub>icm</sub> and then apply the max input swing to get max output symetrical swing.
- To find out the differential gain i.e A<sub>vdm</sub>:
  ![Image](https://github.com/user-attachments/assets/bbfd2bfd-1b54-497b-b9e3-119f4e4d2727)
  - From the graph A<sub>vdm</sub> = (V<sub>ocm1</sub> - V<sub>ocm2</sub>)/(V<sub>icm1</sub> - V<sub>icm2</sub>)
      - A<sub>vdm</sub> = 614.47mV/100mV
        <table>
          <td>A<sub>vdm</sub> = 6.14 V/V </td>
        </table>
**AC Analysis**
- We have obtained gain from above analysis i.e 6.14V/V
- contvert to dB scale = 20log(A<sub>vdm</sub>)
- dB = 20log(6.14)
<table>
  <td>dB value is 15.763dB</td>
</table>
  - lets verify this with the graph
  
  ![Image](https://github.com/user-attachments/assets/9c76c677-adb3-4881-9b6b-7bfe723ffcf5)
  3dB will be 12.76dB
  3dB bandwidth will be 21.56 GHz
## Circuit 3
- The R<sub>D</sub> resistances are replaced by the diode connected PMOS.This diode connected MOS will be always in the saturation region.
  
  ![Image](https://github.com/user-attachments/assets/a9708137-5a58-4279-b62d-cfaecb450e91)
  **DC Analysis**
  ![Image](https://github.com/user-attachments/assets/c4c8ab0a-8d8c-4bba-9f19-3f2ba02baed7)
  **Transient Analysis**
![Image](https://github.com/user-attachments/assets/b67feec8-f102-4216-81ed-e0da8c5a981e)
- From the graph A<sub>vdm</sub> = (V<sub>ocm1</sub> - V<sub>ocm2</sub>)/(V<sub>icm1</sub> - V<sub>icm2</sub>)
      - A<sub>vdm</sub> = 183.47mV/100mV
        <table>
          <td>A<sub>vdm</sub> = 1.83 V/V </td>
        </table>
  **AC Analysis
  ![Image](https://github.com/user-attachments/assets/a6c33d00-7d1c-4c84-94f6-e11521639fa6)
  contvert to dB scale = 20log(A<sub>vdm</sub>)
- dB = 20log(1.83)
<table>
  <td>dB value is 5.24dB</td>
</table>
- <p>In this circuit when I try </p>



  ## Result
  **With respect to the V<sub>icm</sub> with +- 0.5V**
  <table>
     <tr>
        <td>V<sub>icm</sub> (V)</td>
        <td>V<sub>ocm</sub> (V)</td>
        <td>I<sub>D</sub> (mA)</td>
        <td>V<sub>p</sub> (V)</td>
        <td>I<sub>ss</sub> (mA)</td>
        <td>A<sub>v</sub> (V/V)</td>
       <td>Observations</td>
     </tr>
     <tr>
       <td>0.8</td>
       <td>2.12</td>
       <td>0.207</td>
       <td>0.172</td>
       <td>0.41443</td>
       <td>4.069</td>
       <td> a) the V<sub>ocm</sub> will increase.
      b) the I<sub>D</sub> will decrease.
      c) the A<sub>v</sub> will decrease.
      d) the total current I<sub>ss</sub> will decrease.
      e) the nodal voltage Vp will decrease.</td>
     </tr>
     <tr>
       <td>1.3</td>
       <td>1.4</td>
       <td>0.6</td>
       <td>0.5</td>
       <td>1.2</td>
       <td>5</td>
       <td>It is as per the given question </td>
     </tr>
     <tr>
       <td>1.8</td>
       <td>0.894</td>
       <td>0.875</td>
       <td>0.728</td>
       <td>1.751</td>
       <td>2.799</td>
       <td> 
       a) the V<sub>ocm</sub> will decrease.
       b) the I<sub>D</sub> will increase.
       c) the A<sub>v</sub> will increase.
       d) the total current I<sub>ss</sub> will increase.
       e) the nodal voltage Vp will increase.</td>
     </tr>
  </table>

**Comparision based on the obtained Values**
  
  <table>
    <tr>
      <td>Parameters</td>
      <td> Calculated</td>
      <td>Circuit 1 (with R<sub>ss</sub>)</td>
      <td>Circuit 2 (with constant current source)</td>
      <td>Circuit 3 (with NMOS)</td>
      <td>Observation</td>
    </tr>
    <tr>
      <td>V<sub>icm</sub></td>
      <td>1.3V</td>
      <td> 1.3V</td>
      <td>1.3V</td>
      <td>1.3V</td>
      <td>As per the design </td>
    </tr>
    <tr>
      <td>V<sub>ocm</sub></td>
      <td> 1.4V</td>
      <td>1.40V</td>
       <td>1.4V</td>
        <td>1.39901V</td>
        <td><p>Its as per the simulation , if we need to increase the V<sub>ocm</sub> then either we need to decrease R<sub>D</sub> or I<sub>D</sub> , if we need to decrease the V<sub>ocm</sub> then either we need to **increase R<sub>D</sub> or I<sub>D</sub></p></td>
    </tr>
    <tr>
      <td>V<sub>p</sub></td>
      <td>0.5V</td>
      <td>0.5V</td>
      <td>0.5V</td>
      <td>0.5748V</td>
      <td><p>It's Nodal  Voltage due to replacement of MOSFET its value </p></td>
    </tr>
    <tr>
      <td>I<sub>D</sub></td>
      <td>0.6mA</td>
      <td>0.599mA</td>
      <td>0.6mA</td>
      <td>0.6mA</td>
      <td>If I<sub>D</sub> has to be incresed then we need to decrease the Aspect Ratio(W/L).If I<sub>D</sub> has to be decreased then we need to increase the Aspect Ratio(W/L).
      </td>
    </tr>
    <tr>
      <td>I<sub>ss</sub></td>
      <td>1.2mA</td>
      <td>1.198mA</td>
      <td>1.2mA</td>
      <td>1.2mA</td>
      <td>It's the total current flowing in the differential amplifier and its also called as <em>Tail Current</em></td>
    </tr>
    <tr>
      <td>R<sub>D</sub>
      <td>1.833KΩ</td>
      <td>1.8337kΩ</td>
      <td>1.83333KΩ</td>
      <td>1.8337kΩ</td>
      <td>AS we need to set the V<sub>ocm</sub> as per that the R<sub>D</sub> values has Changed.</td>
    </tr>
    <tr>
      <td>g<sub>m</sub></td>
      <td>2.77mS</td>
      <td>2.47mS</td>
      <td>2.47mS</td>
      <td>3.3551mS</td>
      <td><p>From calculation the g<sub>m</sub>has been decreased due to differ in the V<sub>th</sub> value.The g<sub>m</sub> value has been increased due to decrease in the V<sub>ov</sub></p></td>
    </tr>
    <tr>
      <td>A<sub>vdm</td>
        <td>-4.99V/V</td>
        <td>-4.528 V/V</td>
        <td> -4.528 V/V</td>
        <td> -6.14 V/V</td>
        <td><p>The is differ from the calculated value because change in the g<sub>m</sub> value .The gain has increased because  the MOSFET acts like a very high impedance load, leading to a larger voltage swing across the drain.</p></td>
    </tr>
        <tr>
          <td>Gain in dB scale(20log(A<sub>vdm</sub>) </td>
          <td>13.96dB</td>
          <td>13.18dB</td>
          <td>13.18dB</td>
          <td>15.76dB</td>
          <td>We can see variation because the gain has been increased</td>
        </tr>
        <tr>
          <td>Bandwidth</td>
          <td>-</td>
          <td>19.433GHz</td>
          <td>19.433GHz</td>
          <td>21.56GHz</td>
          <td><p> When compare to Resistor and constant current source the Mosfet Bandwidth has been increased because the MOSFET's high input impedance it reduces the loading effect, allowing for a wider range of frequencies to get amplified without any signal distortion. </p></td>
        </tr>
         </table>
        
## Inference
- The differential amplifier circuit was successfully designed and analyzed.
- Changing Vicm affects Vocm, ID, and gain (Av).
- Replacing Rss with a constant current source improves circuit performance.
- Using NMOS instead of a resistor improves stability and current sourcing capabilities.
- V<sub>icm</sub> must be within the range that keeps both input transistors ON and in saturation.
- Larger Amplitude Causes Early Distortion i.e at higher ampltitude transistor reaches triode or cutoff region , so we need to apply V<sub>icm</sub> within the calculated range.
- We need design the baised voltage i.e V<sub>b</sub> as such the NMOS 3 will operate in the saturation region .
-  <p>V<sub>GS1</sub> + V<sub>ov3</sub> <= V<sub>icm</sub> <= min(V<sub>DD</sub> - (I<sub>D</sub>*R<sub>D</sub>) + V<sub>th</sub> , V<sub>DD</sub>(when one mosfet is off)) this the Range calculation of V<sub>icm</sub>.</p>







  
  
    
