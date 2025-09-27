Got it\! Let's integrate the **"Logic Gate Flip"** (RTL ➡️ Gate 🔄) into Day 1 of Week 1, along with the **"Tapeout Flash"** and the **Progress Bar** for a highly visual and dynamic progress report.

Here is the final, fully animated-with-Unicode markdown file:

-----

# 🚀 VSD RISC-V SoC Tapeout Journey

> **Repository Log:** Documenting the end-to-end journey of building a RISC-V based SoC, as part of the **VSD RISC-V SoC Tapeout Program**.

**Progress to Tapeout:** **[▓▓░░░░░░░░] 20% Complete** ⏳

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

## 🙏 Gratitude & Acknowledgment

This world-class learning opportunity is made possible by the dedication of the VSD team.

> A huge thank you to **Kunal Ghosh** sir and the entire **VSD (VLSI System Design) team** for organizing the RISC-V SoC Tapeout Program and providing this crucial learning path free of cost. **\#RISCV** **\#Tapeout**

-----
