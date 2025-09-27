# VSD RISC-V SoC Tapeout Program

Repository containing my work for the **VSD RISC-V SoC Tapeout Program**, documenting the end-to-end journey of learning to build a RISC-V based SoC.  

---

## 📅 Weekly Progress

### Week 0 – Getting Started with SoC & Tools Installation
- Installed required tools (e.g., **Yosys**, **iverilog**, **gtkwave**, **ngspice**, etc.).
- Set up the working environment on Ubuntu.
- Understood the basics of SoC design flow: Specification → RTL design → Functional Verification → Synthesis → SoC Integration → Floorplanning → Placement → CTS → Routing → GDSII generation → DRC/LVS checks → Fabrication (Tapeout → Tapein).

### Week 1 – RTL Design and Synthesis Basics

#### Day 1 – Verilog Simulation and Synthesis
🔹 Key Learnings  
- Simulate a Verilog design using **Icarus Verilog (iverilog)**  
- View output waveforms using **GTKWave**  
- Synthesize the design with **Yosys**  

#### Day 2 – Verilog & Synthesis
🔹 Key Learnings  
- Understand the **Sky130 Library**  
- Learn about **Hierarchical vs. Flattened Synthesis**  
- Explore different **Types of D Flip-Flops (DFFs)**  

#### Day 3 – Combinational & Sequential Optimization
🔹 Key Learnings  
- Learn about **Constant Propagation**  
- Understand **State Optimization**  
- Explore **Cloning**  
- Study **Retiming**  

#### Day 4 – Gate-Level Simulation (GLS) & Key Concepts
🔹 Key Learnings  
- Perform **Gate-Level Simulation (GLS)** using Sky130 standard cell library  
- Understand **Blocking vs. Non-Blocking assignments** in Verilog  
- Learn about **Synthesis–Simulation Mismatch** and how to avoid it  

#### Day 5 – Optimization in Synthesis
🔹 Key Learnings  
- Understand **If-Else statements** in Verilog and their effect on synthesis  
- Learn about **Inferred Latches** in Verilog and why they should be avoided  
- Explore the role of **For Loops** in Verilog  
- Use **Generate Blocks** in Verilog for scalable design  
- Introduction to **Ripple Carry Adder (RCA)** in digital logic  

---

## 🙏 Acknowledgment  

I am thankful to **Kunal Ghosh** sir and the **VSD (VLSI System Design) team** for organizing the RISC-V SoC Tapeout Program free of cost.  
