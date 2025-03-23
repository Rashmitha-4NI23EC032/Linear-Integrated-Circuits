##  Current Mirror
<p>A current mirror circuit is a fundamental building block in analog electronics used to replicate a reference current with high accuracy. It is widely employed in biasing, active loads, and current sources in integrated circuits . The ideal current mirror maintains a stable output current regardless of variations in process, supply voltage, and temperature (PVT).</p>

## Principle of Operation
<p>A basic current mirror consists of two matched  MOSFETs. The first transistor is configured to establish a reference current, and the second transistor mirrors this current by operating under the same conditions. However, practical current mirrors are affected by PVT variations, leading to deviations in the mirrored current.</p>

![Image](https://github.com/user-attachments/assets/40c28843-6481-401d-9019-d5595e54c03a)

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
    ![Image](https://github.com/user-attachments/assets/2c02ec6e-5197-41c7-8d38-57927a7e6fef)
   - Depend on the sizing parameters.
- PMOS current Mirroring
   - Uses: P-channel MOSFETs
   - The reference current is set using a diode-connected PMOS transistor, and another PMOS mirrors it.
