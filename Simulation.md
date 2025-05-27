## Abstract
This paper compares two types of Operational Transconductance Amplifiers (OTAs): the Recycled Folded Cascode (RFC) OTA and the Miller Compensated OTA. The RFC OTA improves performance by reusing current inside the circuit, which helps achieve high gain and bandwidth without using much power. On the other hand, the Miller OTA uses two stages and a special capacitor (Miller capacitor) to make the circuit more stable, especially when driving large loads. Simulations show that the RFC OTA gives better gain and speed with lower power use, while the Miller OTA offers better stability and is easier to design for high load conditions. This comparison helps choose the right OTA for different analog circuit applications.
## 	INTRODUCTION
Operational Transconductance Amplifiers (OTAs) play a vital role in analog and mixed-signal integrated circuits, where gain, bandwidth, power efficiency, and stability are critical performance parameters. Among various OTA architectures, the Miller Compensated OTA and Recycled Folded Cascode (RFC) OTA have emerged as widely used designs due to their distinct advantages in different applications.
The Miller Compensated OTA is a classical
two-stage amplifier topology, known for its ability to achieve high gain while maintaining stability through the use of Miller compensation. It is often preferred in applications were driving large capacitive loads and achieving good phase margin are essential. However, this topology typically suffers from limited gain-bandwidth product (GBW) and slower transient response due to internal compensation.
In contrast, the Recycled Folded Cascode OTA is a modified single-stage design that reuses the bias current and internal signal paths to enhance transconductance and gain without significantly increasing power consumption. This makes the RFC OTA well-suited for low-power and high- speed applications. By recycling current from internal nodes, it offers improved efficiency and bandwidth compared to traditional folded cascode or Miller architectures.
This paper presents a detailed comparative study of both architectures in terms of key performance such as gain, GBW, phase margin, power consumption
## 	DESIGN OVERVEIW
**Recycled Folded Cascode OTA**
The Recycled Folded Cascode OTA is based on a traditional folded cascode topology but includes additional transconductance paths and current- reuse techniques to enhance performance. In this architecture, the current from the folded cascode input stage is reused by a secondary gain-boosting path, effectively increasing the output resistance and overall gain. The recycling path improves the transconductance without a corresponding increase in power or area. This design is inherently single-stage, which provides wide bandwidth and better frequency response due to the absence of Miller compensation. It is particularly suited for low-voltage, low-power applications requiring high-speed operation.
## Simulation 
![Image](https://github.com/user-attachments/assets/4fcb79e8-e3e7-4857-8e90-2c1b4a65ab11)
- For	design	of	RFC	using	gm/ID	methodology specifications are
- Unity gain bandwidth = 120MHz Load capacitance = 5.6pF Parameter K =3
- Supply voltage =1.2v
- The UGB is taken as 120MHz. The relation between transconductance of the OTA and the UGB is given by
- 𝐺𝑚𝑅𝐹𝐶 = 𝜔𝑡𝐶𝐿
- The transconductance of the input transistor is given as
- 𝐺𝑚𝑅𝐹𝐶 = 𝑔𝑚1𝑎(1 + 𝑘)
- The 𝑔𝑚1𝑎 gives the transconductance of the input PMOS transistor named as M1a. The value of K is assumed to be 3. The input transconductance
required for the UGB is found by substituting
- 𝑔𝑚1𝑎=(1 + 𝑘) = 𝜔𝑡𝐶𝐿
By putting all the values in the above equation the transconductance of the input transistor required is 1.05mS. The DC current required for getting the transconductance is given by
- 𝐼𝐷1𝑎 =𝑔𝑚1𝑎𝑔𝑚⁄𝐼𝐷
The power consumption depends on the 𝑔𝑚⁄𝐼𝐷 . As we are operating in moderate inversion, the gm/ID is chooen to be moderately high so the power consumption is decreased and the parasistic capacitance is very less compared to weak inversion. We assumed a gm/ID of 21. So the input DC current is found to be 50uA. The transcondcutance of M1a and M2a are assumed to be equal so the power consumed by them are also same. M1a and M2a comprises the half circuit so the power consumption by M1a, M2a, M3a and M4a is  4ID.  So  the  current  flowing  through M0 is 200uA. As we have assumed K as 3 so the transconductance of M3a is 3 times that of the M3b. The transconductance of M3a is 3.15mS. By choosing same   𝑔𝑚⁄𝐼𝐷   for   M1a   and   M3a   the three times of input so the DC current is 150uA. By applying KCL at the cascode node the current flowing in M1a is 50uA and current flowing in M3a is 150uA so the through M5 and M7 is 100uA. As the path M2b, M11 and M3b	acts	as	a	unity gain amplifier so the transconductance of M3b should be same  as  M2b  which  is  same  as  that  of M1a. By choosing the same region of operation the DC current  through  M3b  is  same  as  that  of the M1a and is 50uA. As the current flowing through M5,
M7 and M9 are same so the current
consumed by them is also same 50uA.
- So the total current consumption of the OTA is
- 𝐼𝑅𝐹𝐶 = 8 ∗ 𝐼𝑏𝑖𝑎𝑠 = 400𝑢𝐴
- The power supply voltage used is 1.2volts. So the power consumption is found to be
- 𝑃𝑜𝑤𝑒𝑟𝑅𝐹𝐶 = 1.2 ∗ 𝐼𝑅𝐹𝐶
- PowerRFC =480𝑢𝑊.
## Result 
 ![Image](https://github.com/user-attachments/assets/bdda4300-adc5-4425-bb90-74c1cdb0a292)
 
**DC Gain**: The Miller OTA achieves the highest DC gain due to its two-stage architecture and Miller compensation. However, the EIRFC OTA shows significant gain improvement (62 dB) over the basic RFC due to positive feedback, making it suitable for high-resolution ADC applications.

**Bandwidth**: The GBW of EIRFC (164 MHz) is substantially higher than both Miller (6.25 MHz) and RFC (1.8 MHz), proving the effectiveness of advanced folding and feedback techniques.

**CMRR**: EIRFC offers a dramatic CMRR improvement (66 dB), nearly doubling that of Miller OTA estimates, by suppressing common-mode signals with feedback architecture.

**Power Efficiency**: The RFC OTA is most power-efficient (400 µW), while the Miller OTA, although within 1 mW, uses more power. The EIRFC uses more current but offers better performance metrics.

**Slew Rate**: The Miller OTA's slew rate is modest (10 µV/s), while EIRFC shows a dramatically higher slew rate (39.3 V/µs), crucial for high-speed analog applications.
## Conlusion 
**Enhanced Transconductance Efficiency**
The recycled folded cascode OTA significantly improves transconductance  by reusing bias currents effectively, leading to better current efficiency compared to conventional designs.

**Improved Gain and Bandwidth**
By recycling currents through auxiliary paths, the OTA achieves higher DC gain and broader bandwidth, making it suitable for high-performance analog applications.

**Low Power Consumption**
The topology ensures lower power consumption without sacrificing performance, making it ideal for low-power analog signal processing circuits.

**High Output Swing and CMRR**
The design maintains a relatively high output voltage swing and common-mode rejection ratio, contributing to better linearity and signal integrity.

**Compact and Area-Efficient**
The recycled structure minimizes the need for additional current mirrors or gain stages, helping reduce silicon area in integrated circuits.

**Suitability for Advanced Applications**
Due to its high performance and power efficiency, the recycled folded cascode OTA is well-suited for use in analog front-ends, ADCs, and biomedical sensor interfaces.



