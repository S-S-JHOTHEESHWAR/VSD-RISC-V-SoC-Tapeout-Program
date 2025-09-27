
# Day 5 – Optimization in Synthesis

## 📌 Tasks
1. Understand **If-Else statements in Verilog** and their effect on synthesis.  
2. Learn about **Inferred Latches in Verilog** and why they should be avoided.  
3. Explore the role of **For Loops in Verilog**.  
4. Use **Generate Blocks in Verilog** for scalable design.  
5. Introduction to **Ripple Carry Adder (RCA)** in digital logic.  

---

## 🔹 1. If-Else Statements in Verilog

- If-Else is used to describe **conditional logic**.  
- Synthesizers map nested If-Else to **priority encoders**.  
- For parallel conditions, use **Case statements** instead (optimized for hardware).  

Example:
```verilog
always @(*) begin
  if (sel == 2'b00) y = a;
  else if (sel == 2'b01) y = b;
  else if (sel == 2'b10) y = c;
  else                  y = d;
end
```

---

## 🔹 2. Inferred Latches in Verilog

* A latch is inferred when not all conditions of a combinational block are specified.
* This causes unintended storage, which is usually **undesirable in synthesis**.

Example (bad):

```verilog
always @(*) begin
  if (enable)
    q = d;   // No else → synthesizer infers a latch
end
```

✅ Fix by covering all branches:

```verilog
always @(*) begin
  if (enable)
    q = d;
  else
    q = 0;
end
```

---

## 🔹 3. For Loops in Verilog

* **For loops in synthesizable Verilog are unrolled** during synthesis.
* They are useful for repetitive hardware structures like adders, shifters, and multiplexers.
* Loops must have **static limits** known at compile time.

Example:

```verilog
integer i;
always @(*) begin
  sum = 0;
  for (i = 0; i < 8; i = i + 1)
    sum = sum + data[i];
end
```

---

## 🔹 4. Generate Blocks in Verilog

* `generate` allows **parametric and scalable hardware instantiation**.
* Often used to replicate modules or logic based on a parameter.

Example:

```verilog
genvar i;
generate
  for (i = 0; i < 4; i = i + 1) begin : adder_array
    full_adder fa (.a(a[i]), .b(b[i]), .cin(c[i]), .sum(s[i]), .cout(c[i+1]));
  end
endgenerate
```

---

## 🔹 5. Ripple Carry Adder (RCA)

* RCA is a basic form of binary adder built using **a chain of full adders**.
* Each adder waits for the carry-out of the previous stage → hence the name *ripple*.
* Simple to design, but **slow for large bit-widths** due to carry propagation delay.



---

## 🎯 Summary

* ✅ **If-Else** → priority logic, use carefully (case preferred for parallel conditions).
* ✅ **Inferred Latches** → result from incomplete assignments, avoid them.
* ✅ **For Loops** → unrolled by synthesis, good for repetitive logic.
* ✅ **Generate Blocks** → scalable, parameterized hardware instantiation.
* ✅ **Ripple Carry Adder (RCA)** → simple but slow adder due to carry ripple delay.

---


