

# 🚀 Week 5 – OpenROAD Flow: Floorplan & Placement

## 🛠️ 1. OpenROAD Installation

### 📥 Clone the Repository
```bash
git clone https://github.com/The-OpenROAD-Project/OpenROAD-flow-scripts.git
cd OpenROAD-flow-scripts
```

### ⚙️ Build OpenROAD
```bash
make OPENROAD_EXE=$(pwd)/tools/OpenROAD/bazel-out/k8-opt-exec-ST-*/bin/openroad
```

### ✅ Verify Environment Setup
```bash
source ~/OpenROAD-flow-scripts/setup_env.sh
```

Expected terminal output:
- `OpenROAD Environment Setup Complete`
- `Flow.tcl loaded successfully`

---

## 📂 2. Flow Execution & GUI Visualization

### 📍 Navigate to Design Flow Directory
```bash
cd <path-to-gcd-flow-directory>
```

### 🖥️ Launch GUI for Final Design
```bash
make gui_final
```

### 👀 Observations in GUI
- Floorplan generated for the `gcd` module
- Standard cells placed successfully
- Wires and interconnects visible in 2D layout

### 📋 Terminal Logs Confirmed
- `Floorplan stage completed`
- `Placement stage completed`
- `Core area: <value>`
- `Die dimensions: <value>`

---

## 📝 3. Summary

- Successfully installed and verified OpenROAD environment
- Executed flow for `gcd` using `make gui_final`
- Verified floorplan and placement stages
- Standard cells placed and core area calculated

---

Let me know if you'd like to add screenshots, diagrams, or links to documentation!
