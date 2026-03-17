# JKFLIPFLOP-USING-IF-ELSE

**AIM:** 

To implement  JK flipflop using verilog and validating their functionality using their functional tables

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

**JK Flip-Flop**

JK flip-flop is the modified version of SR flip-flop. It operates with only positive clock transitions or negative clock transitions. The circuit diagram of JK flip-flop is shown in the following figure.

![image](https://github.com/naavaneetha/JKFLIPFLOP-USING-IF-ELSE/assets/154305477/a649c30b-232b-4558-b188-fd6c09845180)


This circuit has two inputs J & K and two outputs Qtt & Qtt’. The operation of JK flip-flop is similar to SR flip-flop. Here, we considered the inputs of SR flip-flop as S = J Qtt’ and R = KQtt in order to utilize the modified SR flip-flop for 4 combinations of inputs. The following table shows the state table of JK flip-flop.

![image](https://github.com/naavaneetha/JKFLIPFLOP-USING-IF-ELSE/assets/154305477/c4360742-e8a8-4937-b089-c46c0433f9a3)

 
Here, Qtt & Qt+1t+1 are present state & next state respectively. So, JK flip-flop can be used for one of these four functions such as Hold, Reset, Set & Complement of present state based on the input conditions, when positive transition of clock signal is applied. The following table shows the characteristic table of JK flip-flop. Present Inputs Present State Next State
 
![image](https://github.com/naavaneetha/JKFLIPFLOP-USING-IF-ELSE/assets/154305477/6c275261-a6d5-4c37-a3a7-1e88ca11c4cd)

By using three variable K-Map, we can get the simplified expression for next state, Qt+1t+1. Three variable K-Map for next state, Qt+1t+1 is shown in the following figure.
 
![image](https://github.com/naavaneetha/JKFLIPFLOP-USING-IF-ELSE/assets/154305477/5174f41b-0ce0-4329-a372-6d1943ea6673)

The maximum possible groupings of adjacent ones are already shown in the figure. Therefore, the simplified expression for next state Qt+1t+1 is Q(t+1)=JQ(t)′+K′Q(t)Q(t+1)=JQ(t)′+K′Q(t)

**Procedure**

/* write all the steps invloved */

**PROGRAM**

 Program for flipflops and verify its truth table in quartus using Verilog programming. 
 ```
 Developed by:SHAKTHI BALAN V
 RegisterNumber:212225230259
```
 ```
module JK(
    input clk,
    input j,
    input k,
    output reg q,
    output reg qb
);

always @(posedge clk) begin
    if (j == 1'b0 && k == 1'b0) begin
        q  <= q;    // Hold state
        qb <= qb;
    end
    else if (j == 1'b0 && k == 1'b1) begin
        q  <= 1'b0; // Reset to 0
        qb <= 1'b1;
    end
    else if (j == 1'b1 && k == 1'b0) begin
        q  <= 1'b1; // Set to 1
        qb <= 1'b0;
    end
    else begin      // j==1 && k==1: Toggle
        q  <= ~q;
        qb <= ~qb;
    end
end

endmodule
```


**RTL LOGIC FOR FLIPFLOPS**

<img width="671" height="339" alt="Screenshot 2026-03-12 104844" src="https://github.com/user-attachments/assets/2c4f720c-6a2b-4802-8301-dab50c55c622" />


**TIMING DIGRAMS FOR FLIP FLOPS**
![WhatsApp Image 2026-03-17 at 3 38 23 PM](https://github.com/user-attachments/assets/240015a2-c41b-42e4-b901-4d5ee4a903e9)



**RESULTS**
Thus,the code executed successfully
