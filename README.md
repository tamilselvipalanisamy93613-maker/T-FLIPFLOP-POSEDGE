# T-FLIPFLOP-POSEDGE

**AIM:**

To implement  T flipflop using verilog and validating their functionality using their functional tables

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

**T Flip-Flop**

T flip-flop is the simplified version of JK flip-flop. It is obtained by connecting the same input ‘T’ to both inputs of JK flip-flop. It operates with only positive clock transitions or negative clock transitions. The circuit diagram of T flip-flop is shown in the following figure.

![image](https://github.com/naavaneetha/T-FLIPFLOP-POSEDGE/assets/154305477/458a68fe-2d08-4a9d-ac4f-7ae0480ce0bd)

 
This circuit has single input T and two outputs Qtt & Qtt’. The operation of T flip-flop is same as that of JK flip-flop. Here, we considered the inputs of JK flip-flop as J = T and K = T in order to utilize the modified JK flip-flop for 2 combinations of inputs. So, we eliminated the other two combinations of J & K, for which those two values are complement to each other in T flip-flop. The following table shows the state table of T flip-flop.

Here, Qtt & Qt+1t+1 are present state & next state respectively. So, T flip-flop can be used for one of these two functions such as Hold, & Complement of present state based on the input conditions, when positive transition of clock signal is applied. The following table shows the characteristic table of T flip-flop. Inputs Present State Next State

![image](https://github.com/naavaneetha/T-FLIPFLOP-POSEDGE/assets/154305477/cdd7fb32-539f-4b66-bb8d-f305a153c886)

 
From the above characteristic table, we can directly write the next state equation as Q(t+1)=T′Q(t)+TQ(t)′ ⇒Q(t+1)=T⊕Q(t)

**Procedure**
 1.Declare T, clk, Q.

2.Use always @(posedge clk).

3.If T = 1 → toggle Q.

4.If T = 0 → hold Q.

5.End module.


**PROGRAM**

Program for flipflops and verify its truth table in quartus using Verilog programming.
```
 module t_ff ( input wire clk, rst, T, output reg Q
);

initial begin Q<=1'b0; end

 always @(posedge clk or posedge rst) begin

    if (rst)
        Q <= 1'b0;       // Reset
    else if (T)
        Q <= ~Q;         // Toggle if T=1
    else
        Q <= Q;          // Hold if T=0
end
endmodule
```
**RTL LOGIC FOR FLIPFLOPS**
<img width="1487" height="701" alt="Screenshot 2025-12-15 133205" src="https://github.com/user-attachments/assets/38f0277b-f732-4f7b-ae1c-0ad588288a07" />

**TIMING DIGRAMS FOR FLIP FLOPS**
<img width="1195" height="576" alt="Screenshot 2025-12-15 133219" src="https://github.com/user-attachments/assets/eb40eaf2-d5ba-4877-a722-202ed640be16" />

**RESULTS**
The T flipflop using verilog and validating their functionality using their functional tables is verified.
