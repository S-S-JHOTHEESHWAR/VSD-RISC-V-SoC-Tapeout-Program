

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


### 🚀 Week 3 – Post-Synthesis Verification: GLS & STA

> "From RTL to Reality – BabySoC passes the gate-level test!"

---

### 🔹 Gate-Level Simulation (GLS)
✅ **Objective:** Verify BabySoC functionality after synthesis  
- Ran GLS on the **synthesized netlist** using **Icarus Verilog**  
- Compared GLS waveforms with RTL simulation to confirm **functional correctness**  
- Checked module interactions: **RVMYTH core ↔ PLL ↔ DAC**  

💡 **Key Insight:** All signals propagated correctly post-synthesis – BabySoC “still alive” at gate level!

---

### 🔹 Static Timing Analysis (STA)
⏱️ **Objective:** Ensure timing correctness of the design  
- Performed **STA using OpenSTA**  
- Verified **setup & hold checks**, **slack**, and **critical paths**  
- Generated timing reports:
  - **Worst Negative Slack (WNS)** ✅  
  - **Total Negative Slack (TNS)** ✅  

💡 **Key Insight:** BabySoC meets all timing constraints – ready for safe operation at target frequency!

---

### 🎯 Outcome
- BabySoC passed **both GLS and STA checks**  
- Ensured design is **functionally robust** and **timing-correct** post-synthesis  
- Foundation ready for **integration and floorplanning** in upcoming weeks



## 🙏 Gratitude & Acknowledgment

This world-class learning opportunity is made possible by the dedication of the VSD team.

> A huge thank you to **Kunal Ghosh** sir and the entire **VSD (VLSI System Design) team** for organizing the RISC-V SoC Tapeout Program and providing this crucial learning path free of cost. **\#RISCV** **\#Tapeout**

-----
