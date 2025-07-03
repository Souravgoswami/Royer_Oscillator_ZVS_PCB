# Royer Oscillator with ZVS for Induction Heating / Transformer Drive

This project features a Royer oscillator circuit with Zero Voltage Switching (ZVS) capability, optimized for high-frequency AC generation to drive small induction heaters or high-frequency transformers. The design uses a dual inductor tank circuit, MOSFET-based switching, and an auxiliary power stage for polarity protection and soft-start.

### Key Features

* **ZVS Royer Oscillator Topology** for efficient high-frequency AC generation
* **Dual inductor tank circuit** (L1, L2) with parallel resonant capacitors for energy-efficient oscillation
* **IRFP4115 MOSFETs** with Zener and TVS diode protection
* **MP1584EN Buck Converter Stage** for regulated supply with polarity protection and relay-controlled hard-start.
* **Relay-based hard start**: Ensures full supply voltage is applied abruptly to initiate stable oscillation; avoids the failure modes observed with soft-start circuits.
* **Suitable for:**
  * Induction heating applications
  * Flyback or HF transformer driving
  * CCFL backlighting or wireless power experiments

### Components:
  * **2x TO-220 IRFP4115 HEXFET MOSFETs**: High-current N-channel MOSFETs for ZVS switching.
  * **2x Metallized Polypropylene Tank Capacitors**: Film or ceramic capacitors rated for high current and frequency (2x in parallel to reduce ESR and ESL). Must be rated for > 150V with ESR <= 0.002Ω.
  * **2x Inductors**: Use high-flux cores such as Sendust (e.g. KS157-125A) or nanocrystalline/Hi-Flux/MPP cores. Iron powder may overheat significantly and is way less efficient. Ferrite (MnZn) cores are not suitable for this application due to saturation at high currents.
  * **5x US1M Diodes**: - Ultra-fast recovery diodes for transient protection, polarity protection, cross-coupled gate drive diodes.
  * **2x P6KE100A (x2)**: Used to protect MOSFET drain-source.
  * **2x P6KE24A**: For overvoltage suppression on 28V buck converter.
  * **2x 1W 12V Zener Diodes**: Gate voltage clamping.
  * **2x 3W 330Ω Gate Resistors**: To control gate charging rate.
  * **1x MP1584EN Buck Converter**: For regulated low-voltage supply.
  * **1x 15A Sugar-cube Relay**: For polarity protection and hard-start functionality.
  * **3x 1206 4.7kΩ Resistors (472)**: Connected between MOSFET gate and ground to ensure they turn off when not actively driven, and to limit LED current.
  * **1x 3mm Red/Green/Blue LED**: Status indicator.
  * **5x 10µF 1206 X7R Ceramic Capacitors (C106)**: 2x across the buck converter for decoupling, 3x across the relay coil to provide soft turn-off (de-energizing delay).

### Previews:

#### Schematic:
![Schematic](https://github.com/Souravgoswami/Royer_Oscillator_ZVS_PCB/blob/main/images/schematic.png)

#### PCB Top:
![Schematic](https://github.com/Souravgoswami/Royer_Oscillator_ZVS_PCB/blob/main/images/pcb_top.png)

#### PCB Bottom:
![Schematic](https://github.com/Souravgoswami/Royer_Oscillator_ZVS_PCB/blob/main/images/pcb_bottom.png)
