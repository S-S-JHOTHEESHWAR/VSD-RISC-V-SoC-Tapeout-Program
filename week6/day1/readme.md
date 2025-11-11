
# 🧠 Day 1 – ASIC Design Flow (OpenLane + SKY130 PDK)

This document explains the basic stages of a **typical ASIC physical design flow** using **open-source EDA tools** and the **SkyWater 130 nm Process Design Kit (SKY130 PDK).**

---

## ⚙️ Overview

**Goal:** Convert RTL (Verilog) design into a final GDSII layout ready for fabrication  
**Flow Manager:** [OpenLane](https://github.com/The-OpenROAD-Project/OpenLane)  
**Technology:** SKY130 PDK (from [Google + SkyWater](https://skywater-pdk.readthedocs.io))

---

## 🧩 ASIC Design Flow – Simple Stages

| **Stage** | **Description** | **Open-Source Tool Used** |
|------------|------------------|----------------------------|
| **1. Logic Synthesis** | Converts RTL (Verilog) into a gate-level netlist using standard cells. | 🧰 **Yosys** |
| **2. Technology Mapping** | Maps generic logic gates to specific cells in the technology library. | ⚡ **ABC (part of Yosys)** |
| **3. Static Timing Analysis (STA)** | Checks setup/hold timing of paths to ensure timing closure. | ⏱️ **OpenSTA** |
| **4. Floorplanning** | Defines core area, aspect ratio, and cell placement regions. | 🏗️ **OpenROAD** |
| **5. Power Planning** | Adds power (VDD) and ground (VSS) rails; builds power distribution network (PDN). | ⚡ **OpenROAD** |
| **6. Placement** | Places standard cells (global + detailed). | 📦 **OpenROAD** |
| **7. Clock Tree Synthesis (CTS)** | Distributes the clock evenly with minimal skew. | ⏰ **TritonCTS** |
| **8. Routing** | Connects all signals using metal layers. | 🛠️ **TritonRoute / OpenROAD** |
| **9. Design Rule Check (DRC)** | Ensures layout follows fabrication design rules. | 🧪 **Magic** |
| **10. Layout vs. Schematic (LVS)** | Verifies layout connectivity matches netlist. | 🔍 **Netgen** |
| **11. Layout Visualization** | View final layout and GDS files. | 🖼️ **KLayout** |

---

## 🧭 OpenLane Flow Summary

OpenLane automates all the above steps through its integrated flow:

```
RTL → Synthesis → Floorplan → Placement → CTS → Routing → DRC/LVS → GDSII
```

Each step can also be run individually using:
```bash
./flow.tcl -design <design_name> -to <stage_name>
```

---

## 🧰 Tools Stack Used

* **Yosys** – Logic Synthesis  
* **ABC** – Technology Mapping  
* **OpenSTA** – Timing Analysis  
* **OpenROAD** – Floorplanning, Placement, and Routing  
* **TritonCTS** – Clock Tree Synthesis  
* **TritonRoute** – Signal Routing  
* **Magic** – DRC Check  
* **Netgen** – LVS Verification  
* **KLayout** – Layout Viewing  

---

## 🧱 PDK Used

* **SKY130 PDK**: Open-source 130 nm process design kit  
  Provided by **SkyWater Technology** and **Google**

---
## lab works
![1](week6/day2/1.png)
![2](week6/day2/2.png)

## 📚 References

* [OpenLane Documentation](https://openlane.readthedocs.io)
* [SkyWater SKY130 PDK](https://github.com/google/skywater-pdk)
* [The OpenROAD Project](https://github.com/The-OpenROAD-Project)

---

**End of Day 1 – Basic ASIC Design Flow Overview 🚀**
```

---

Let me know if you'd like to add your own screenshots, logs, or results from running PicoRV32 through the flow!
