<em>Experiment 1</em>
<br><em>Aim:</em> DC,AC,Transient analysis of Common Source NMOS Amplifier</br>
<br>**Abstract**:<p> The DC,AC and Transient analysis of common source amplifier(CS) using LT spice is used to understand the characterstic of the given circuit. The DC Analysis is used to determine the Operating point(Qpoint) of the circuit ensuring proper baising for the linear opearation.The AC Analysisis used to evaluate the amplifiers frequency response,Gain,Phase shift,and the bandwidth of the circuit. The Transient Analysis is used to get to know the amplifiers response of input with respect to the time.The simulation results will provide the Amplifiers gain stability,bandwidth and the transient behaviour which are essential during the design of the circuit.</p></br> 
<br>**Introduction**:<p> The common source amplifier is the fundamental circuit in the Analog domain which are used for the signal amplification for the various applications.It is the basic configuration of the MOSFET(Metal oxide semiconductor field effective transistor) where the input is giveto the gate terminal and output is driven form the drain terminal and the source is grounded .This amplifier will give the significant gain which is ideally 1 and this amplifier will act as the buffer amplifier which as 180 degree phase shift.</p><p>For the study of this amplifier we have used the LT spice software for the DC ,AC ans transient Analysis of the circuit.The DC Analysis is used to determine the Q point in such a way that the transistor is operating in the saturtaion region. The AC analysis is used to determine the gain, amplifiers frequency response and the bandwidth of the amplifier.Transient is used to get to know the amplifier's time domain response to an input signal.For this software we have used the library called tsmc018.lib.We need to download the library and dump it into the same folder where the simualtion file is save.</p></br>
<br><em>Design 1</em>:</br>
![Image](https://github.com/user-attachments/assets/b6f85d21-1ce1-452f-a2b8-def507cbb9ba)
<br>**Simulation Results**:</br>
<br>**i) DC Analysis**</br>
<br><p>The DC Analysis is used to determine the Q point in such a way that the transistor is operating in the saturtaion region and ensuring the poper biasing for the linear amplification.</p></br>
![Image](https://github.com/user-attachments/assets/9a5b6602-1f51-40ee-ae98-9c608f4fef62)
<br>V<sub>out</sub>=1.8V , V<sub>in</sub>=0.9V , I<sub>d</sub>=55.5µA.</br>
<br> Given the power dissipation is 100µW, then the current accros the resistor will be I<sub>d</sub>=Power/Voltage =55.5µA.</br>
<br>The output load line equation is given by</br><br>V<sub>out</sub>=V<sub>dd</sub>-(I<sub>d</sub>*R<sub>d</sub>). From this equation we can find out the R<sub>d</sub> value </br>
<table>
  <tr>
    <td>Width(m)</td>
    <td>I<sub>d</sub>(A)</td> 
  </tr>
  <tr>
    <td>0.1µ</td>
    <td>48µ</td>
  </tr>
  <tr>
    <td>0.15µ</td>
    <td>50µ</td>
  </tr>
  <tr>
    <td>1.6µ</td>
    <td>51.4µ</td>
  </tr>
  <tr>
    <td>1.7µ</td>
    <td>52.3µ</td>
  </tr>
  <tr>
    <td>1.9µ</td>
    <td>54.2µ</td>
  </tr>
  <tr>
    <td>0.2µ</td>
    <td>55.2µ</td>
  </tr>
</table>
<br><p>V<sub>ds</sub>=V<sub>d</sub>-V<sub>s</sub>=1.8-0=1.8V</p><p>V<sub>ds</sub> > V<sub>ov</sub> , which indicates its in saturation region .</p><p>The operating point will be (V<sub>ds</sub> , I<sub>d</sub>)
i.e (1.8V,55.2µA).</p></br>

**ii) Transient Analysis**:
<br><p>The simulation techinque used to observe the amplifier's time domain response to an input signal .For input we need to give the sinusodial voltage signal in which the DC offset is 0.9V and the V<sub>peak</sub>is 50mV and the frequency is 1kHz the Ac amplitude will be 1V.We need to select the stop time of 3ms.</p></br>

<br>From graph we can calculate the gain of the circuit </br>
<br>A<sub>v</sub>=V<sub>out/V<sub>in</sub></br>
<br>A<sub>v</sub>=1.75V/950mV</br>
<br>A<sub>v</sub>=1.8V/V</br>
<br>which will match the theortical value calculated by A<sub>v</sub>=gmR<sub>d</sub></br>
<br>where gm=K<sub>n</sub>V<sub>ov</sub></br>
<br> From graph we can clearly observe there is an 180 degree phase shift that is exibited by Common source configuration.</br>
<br>Therefore we can conclude its Gain > 1 and has 180 degree phase shift therefore its an NMOS Common source Amplifier. </br>
<br>**iii) AC Analysis**</br>
<br><p>In this AC Analysis we will evaluate the frequency response cure of the given circuit.By applying the Small signal analysis for the given circuit. In this Analysis we need to check in which frequency it act as a linear amplifier.</p></br>
<br><p>While doing simulation we need to select the decade as type of sweep,with starting frequency as 0.1Hz and the stoping frequency as 1THz.</p></br>
<br>Frequency Response :</br>
 ![Image](https://github.com/user-attachments/assets/aee3eb9a-30bb-4010-8b66-00b9ea072885) 
<br> In this due to higher frequency the Parasitic Capacitor (internal capactiors) will get acctivated.</br>
<br> At lower frequency the coupling Capacitors will get activated.</br>



