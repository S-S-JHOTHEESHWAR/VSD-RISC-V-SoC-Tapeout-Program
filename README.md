

# 🚀 VSD RISC-V SoC Tapeout Journey

> **Repository Log:** Documenting the end-to-end journey of building a RISC-V based SoC, as part of the **VSD RISC-V SoC Tapeout Program**.



-----

## 🗓️ Program Progress: The Foundation is Set

### Week 0 – Launchpad: Getting Started & Toolchain Setup

The mission kicked off with a deep dive into the environment and the complete design flow.

  - 🛠️ **Toolchain Installed:** Essential tools like **Yosys**, **iverilog**, **gtkwave**, and **ngspice** are now operational.
  - 💻 **Environment Ready:** Working environment successfully established on Ubuntu.
  - 🗺️ **SoC Design Flow Mastered:** Gained a solid understanding of the full journey:
    > Specification → RTL Design → Functional Verification → **Synthesis** → SoC Integration → **Floorplanning** → Placement → CTS → Routing → **GDSII Generation** → **DRC/LVS Checks** → **✨ FABRICATION (Tapeout) ✨**

-----

### Week 1 – RTL Design & Synthesis Deep Dive

This week focused on the core translation of logic into physical hardware.

| Day | Topic Focus | 💡 Key Learnings & Milestones |
| :--- | :--- | :--- |
| **Day 1** | **Simulation & Synthesis Basics** | 🔹 Simulated Verilog with **Icarus Verilog (iverilog)**. <br> 🔹 Visualized waveforms using **GTKWave**. <br> 🔹 Performed initial logic **Synthesis** (**RTL ➡️ Gate 🔄**) with **Yosys**. |
| **Day 2** | **Libraries & Hierarchical Design** | 🔹 Explored the **Sky130 Library** and its role in physical design. <br> 🔹 Differentiated between **Hierarchical vs. Flattened Synthesis**. <br> 🔹 Studied various **Types of D Flip-Flops (DFFs)**. |
| **Day 3** | **Combinational & Sequential Optimization** | 🔹 Implemented techniques like **Constant Propagation** and **State Optimization**. <br> 🔹 Examined **Cloning** and **Retiming** to improve performance. |
| **Day 4** | **Verification & Mismatch Prevention** | 🔹 Successfully ran **Gate-Level Simulation (GLS)** using the Sky130 standard cell library. <br> 🔹 Clarified **Blocking vs. Non-Blocking assignments**. <br> 🔹 Learned strategies to avoid **Synthesis–Simulation Mismatch**. |
| **Day 5** | **Verilog Constructs for Hardware** | 🔹 Understood the synthesis impact of **If-Else statements**. <br> 🔹 Identified and learned to avoid **Inferred Latches**. <br> 🔹 Explored the role of **For Loops** and used **Generate Blocks** for scalable design. <br> 🔹 Introduced the **Ripple Carry Adder (RCA)** architecture. |

-----
### ⚙️ Week 2 – RVMYTH Integration & VSDBabySoC Simulation

> “From TL-Verilog to Waves — the BabySoC finally comes alive!”

This week marked a major milestone in the **VSD SoC journey**, transforming design files into a living, breathing SoC.

- 🧠 **RVMYTH Conversion:** Translated the **`rvmyth.tlv`** (TL-Verilog) file into synthesizable **`rvmyth.v`**, enabling smooth integration with the SoC environment.  
- 🧩 **Integration:** Combined the **RVMYTH core**, **PLL**, and **10-bit DAC** to form the complete **VSDBabySoC**.  
- 🧪 **Simulation:** Compiled and simulated the SoC using **Icarus Verilog (iverilog)** for functional verification.  
- 🌊 **Waveform Analysis:** Visualized the output signals in **GTKWave**, confirming proper communication between the processor core, PLL, and DAC modules.  
- 🔍 **Key Insights:** Observed stable clock generation by the PLL, verified RISC-V instruction execution, and confirmed DAC response — bridging digital and analog domains.

> 🚀 **System in Motion:** The BabySoC officially boots into life — running RISC-V instructions, syncing clocks, and pulsing analog outputs.  
> The silicon dream is now **digital reality**.
> "From RTL to Reality – BabySoC passes the gate-level test!"


### Week 3 – Post-Synthesis Verification: GLS & STA

> “Ensuring BabySoC behaves correctly at gate level and meets timing constraints.”

- 🔹 **Gate-Level Simulation (GLS):**  
  - Ran GLS on the synthesized BabySoC netlist using **Icarus Verilog**.  
  - Compared GLS waveforms with RTL simulation to confirm **functional correctness**.  
  - Verified stable interactions between **RVMYTH core, PLL, and DAC** post-synthesis.

- 🔹 **Static Timing Analysis (STA):**  
  - Performed STA using **OpenSTA** to check **setup/hold times, slack, and clock paths**.  
  - Confirmed **timing constraints** were met and the design is free of critical path violations.  
  - Generated reports for **worst negative slack (WNS)** and **total negative slack (TNS)** for documentation.

> ✅ **Outcome:** BabySoC passed both GLS and STA checks, ensuring it is **timing-correct and functionally robust** post-synthesis.


### Week 4 – CMOS Inverter & SPICE Simulation

> “Exploring transistor-level behavior and inverter characteristics using SPICE simulations.”

| Day | Topic Focus | 💡 Key Learnings & Milestones |
| :--- | :--- | :--- |
| **Day 1** | **Introduction to SPICE Simulation** | 🔹 Learned what SPICE is and its role in **CMOS/VLSI circuit verification**. <br> 🔹 Understood DC, AC, and transient analyses. <br> 🔹 Recognized how SPICE helps predict transistor behavior before fabrication. |
| **Day 2** | **NMOS Characteristics Analysis** | 🔹 Analyzed **ID vs VDS** for different **VGS** values. <br> 🔹 Plotted **ID vs VGS** to find threshold voltage and conduction behavior. <br> 🔹 Device dimensions: W = 39 µm, L = 15 µm. |
| **Day 3** | **CMOS Inverter – VTC & Transient Response** | 🔹 Simulated **Voltage Transfer Characteristics (VTC)** with NMOS W = 0.36 µm, PMOS W = 0.84 µm, and CL = 50 fF. <br> 🔹 Ran **transient simulation** (1 ns step, 10 ns total) with pulsed input to observe output switching. |
| **Day 4** | **CMOS Inverter Noise Margin Analysis** | 🔹 Analyzed **VTC** with PMOS W = 1 µm, NMOS W = 0.36 µm, CL = 50 fF. <br> 🔹 Observed logic levels: Vin < ~0.7 V → Vout ≈ 1.8 V, Vin > ~1.0 V → Vout ≈ 0 V. <br> 🔹 Determined **noise margins** (NMH, NML) from VTC. |
| **Day 5** | **VTC Variation & Transistor Sizing Effects** | 🔹 Studied VTC changes with **Vdd** (1.8 V → 0.8 V in 0.2 V steps) and observed reduced logic levels, shifted threshold, and lower gain at lower Vdd. <br> 🔹 Analyzed effects of transistor sizing: PMOS W = 7 µm, NMOS W = 0.42 µm → impact on **drive strength, switching point, and speed**. |




## 🙏 Gratitude & Acknowledgment

This world-class learning opportunity is made possible by the dedication of the VSD team.

> A huge thank you to **Kunal Ghosh** sir and the entire **VSD (VLSI System Design) team** for organizing the RISC-V SoC Tapeout Program and providing this crucial learning path free of cost. **\#RISCV** **\#Tapeout**

-----
