<em>Experiment 1</em>
<br><em>Aim:</em> DC,AC,Transient analysis of Common Source NMOS Amplifier</br>
<br><em>Theory:</em></br><p>The common source amplifier in which the input is given to the gate terminal and output is taken from the drain terminal. The source is common to both the input and output. The common source amplifier has 180 degree phase shift.</p></br>
<br><em>Components Required:</em></br>
<br>Resistor:1k ohms, NCMOS transistor(180nm technology), DC power supply</br>
<br><em>Circuit design : </em></br>
![Image](https://github.com/user-attachments/assets/b6f85d21-1ce1-452f-a2b8-def507cbb9ba)
<br>**i) DC Analysis**</br>
<br><p> In DC Analysis we determiine the Qpoint or the operating point of the transistor. The Q point is crucial as it influences the amplifier gain and the signal swing.</p></br>
![Image](https://github.com/user-attachments/assets/9a5b6602-1f51-40ee-ae98-9c608f4fef62)
<br>From simulation: V<sub>out</sub>=1.8V , V<sub>in</sub>=0.9V , I<sub>d</sub>=55.5µA.</br>
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
<br>V<sub>ds</sub>=V<sub>d</sub>-V<sub>s</sub>=1.8-0=1.8V</br>
<br>V<sub>ds</sub> > V<sub>ov</sub> , which indicates its in saturation region .</br>
<br><p>The DC Analysis is used to check wheather the transistor is acting as an amplifier(saturation region).The operating point will be (V<sub>ds</sub> , I<sub>d</sub>)
i.e (1.8V,55.2µA).</p></br>
<br>**ii) Transient Analysis**</br>
<br><p>The simulation techinque used to observe the response with respect to the time.In this analysis we can determine or verify the gain of the give circuit.For input we need to give the sinusodial voltage signal in which the DC offset is 0.9V and the V<sub>peak</sub>is 50mV and the frequency is 1kHz the Ac amplitude will be 1V.We need to select the stop time of 3m s</p></br>

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
  
<br> In this due to higher frequency the Parasitic Capacitor (internal capactiors) will get acctivated.</br>
<br> At lower frequency the coupling Capacitors will get activated.</br>

