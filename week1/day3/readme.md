# ⚡ Day 3 – Combinational & Sequential Optimization

## 📌 Tasks
1. Learn about **Constant Propagation**  
2. Understand **State Optimization**  
3. Explore **Cloning**  
4. Study **Retiming**  

---

## 🔹 1. Constant Propagation
### 📖 Concept
- Analyzes the design code to identify **variables with constant values**.  
- Replaces them directly, allowing tools to **simplify logic** and **reduce circuit size**.  

### 📝 Example
```verilog
assign y = a & 1'b0;   // always 0
assign z = b | 1'b1;   // always 1
```
- The tool will optimize away the gates since the outputs are constants.  

---

## 🔹 2. State Optimization
### 📖 Concept
- Applies to **Finite State Machines (FSMs)**.  
- Removes **unreachable states** and merges **equivalent states**.  
- Reduces **flip-flop count** and **logic area**.  

### 📝 Example
If a 4-state FSM has a state that is never entered, synthesis tools will remove it, reducing the circuit.  

---

## 🔹 3. Cloning
### 📖 Concept
- **Duplicate logic** to improve timing or reduce routing delay.  
- Helps when one gate is driving a **large fanout** (many loads).  

### 📝 Example
Instead of one gate driving 10 loads, the tool may create 2 copies of the gate, each driving 5 loads, to reduce delay.  

---

## 🔹 4. Retiming
### 📖 Concept
- A sequential optimization technique.  
- Moves **flip-flops across combinational logic** without changing functionality.  
- Goal: improve **timing, performance, and area balance**.  

### 📝 Example
If a long combinational path exceeds timing, registers may be shifted across logic to balance pipeline stages.  

---

## 5. lab work


## 🎯 Summary
- ✅ **Constant Propagation** → replaces constants to simplify logic.  
- ✅ **State Optimization** → removes/merges states in FSMs.  
- ✅ **Cloning** → duplicates logic to reduce fanout delay.  
- ✅ **Retiming** → repositions registers to improve timing.  

---

