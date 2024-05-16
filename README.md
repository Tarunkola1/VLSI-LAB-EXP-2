EXP-2

date:

              SIMULATION AND IMPLEMENTATION OF COMBINATIONAL LOGIC CIRCUITS

AIM: To simulate and synthesis ENCODER, DECODER, MULTIPLEXER, DEMULTIPLEXER, MAGNITUDE COMPARATOR using VIVADO 2023.2

APPARATUS REQUIRED: VIVADO 2023.2

PROCEDURE:

STEP:1 Launch the Vivado 2023.2 software.

STEP:2 Click on “create project ” from the starting page of vivado.

STEP:3 Choose the design entry method:RTL(verilog/VHDL).

STEP:4 Crete design source and give name to it and click finish.

STEP:5 Write the verilog code and check the syntax.

STEP:6 Click “run simulation” in the navigator window and click “Run behavioral simulation”.

STEP:7 Verify the output in the simulation window.

LOGIC DIAGRAM :
ENCODER:

![image](https://github.com/Tarunkola1/VLSI-LAB-EXP-2/assets/161431337/b577f785-c906-423c-bb25-9df123a4dfe9)

VERILOG CODE:
```
module encoder(a,y);
input [7:0]a;
output[2:0]y;
or(y[2],a[6],a[5],a[4],a[3]);
or(y[1],a[6],a[5],a[2],a[1]);
or(y[0],a[6],a[4],a[2],a[0]);
endmodule
```

OUTPUT WAVEFORM:

![image](https://github.com/Tarunkola1/VLSI-LAB-EXP-2/assets/161431337/1a44047d-5c18-4337-9ccb-5a1d0c549c9a)

DECODER LOGIC DIAGRAM:

![image](https://github.com/Tarunkola1/VLSI-LAB-EXP-2/assets/161431337/73f80d36-0d2f-4172-a4b0-8034a6884e11)

VERILOG CODE:
```
module decoder1(a,y);
input [2:0]a;
output[7:0]y;
and(y[0],~a[2],~a[1],~a[0]);
and(y[1],~a[2],~a[1],a[0]);
and(y[2],~a[2],a[1],~a[0]);
and(y[3],~a[2],a[1],a[0]);
and(y[4],a[2],~a[1],~a[0]);
and(y[5],a[2],~a[1],a[0]);
and(y[6],a[2],a[1],~a[0]);
and(y[7],a[2],a[1],a[0]);
endmodule
```

OUTPUT WAVEFORM:

![image](https://github.com/Tarunkola1/VLSI-LAB-EXP-2/assets/161431337/8ba56dfd-1143-4c81-a00a-0fd88a3c9750)

MULTIPLEXER LOGIC DIAGRAM:

![image](https://github.com/Tarunkola1/VLSI-LAB-EXP-2/assets/161431337/b63d9dd2-9ff5-4a09-afd6-9b4c65a7608f)

VEROLOG CODE:
```
module mux(s,c,a);
input [2:0]s;
input [7:0]a;
wire [7:0]w;
output c;
and(w[0],a[0],~s[2],~s[1],~s[0]);
and(w[1],a[1],~s[2],~s[1],s[0]);
and(w[2],a[2],~s[2],s[1],~s[0]);
and(w[3],a[3],~s[2],s[1],s[0]);
and(w[4],a[4],s[2],~s[1],~s[0]);
and(w[5],a[5],s[2],~s[1],s[0]);
and(w[6],a[6],s[2],s[1],~s[0]);
and(w[7],a[7],s[2],s[1],s[0]);
or (c,w[0],w[1],w[2],w[3],w[4],w[5],w[6],w[7]);
endmodule
```

OUTPUT WAVEFORM:

![image](https://github.com/Tarunkola1/VLSI-LAB-EXP-2/assets/161431337/20f5c7b9-23d9-44ca-9805-45c5c61c781d)

DE MULTIPLEXER LOGIC DIAGRAM:

![image](https://github.com/Tarunkola1/VLSI-LAB-EXP-2/assets/161431337/0f9c0372-bef9-4b08-ae61-06c2abe17ebc)

VERILOG CODE:
```
module demux_8(s,a,y);
input [2:0]s;
input a;
output [7:0]y;
and(y[0],a,~s[2],~s[1],~s[0]);
and(y[1],a,~s[2],~s[1],s[0]);
and(y[2],a,~s[2],s[1],~s[0]);
and(y[3],a,~s[2],s[1],s[0]);
and(y[4],a,s[2],~s[1],~s[0]);
and(y[5],a,s[2],~s[1],s[0]);
and(y[6],a,s[2],s[1],~s[0]);
and(y[7],a,s[2],s[1],s[0]);
endmodule
```

OUTPUT WAVEFORM:

![image](https://github.com/Tarunkola1/VLSI-LAB-EXP-2/assets/161431337/ffb68bc8-c4bc-4f1f-9bb4-546cc3e3f622)

MAGNITUDE COMPARATOR :

![image](https://github.com/Tarunkola1/VLSI-LAB-EXP-2/assets/161431337/d49ea446-5854-476d-a9c9-56711b6e253a)

VERILOG CODE:
```
module comparator(a,b,eq,lt,gt);
input [3:0] a,b;
output reg eq,lt,gt;
always @(a,b)
begin
 if (a==b)
 begin
  eq = 1'b1;
  lt = 1'b0;
  gt = 1'b0;
 end
 else if (a>b)
 begin
  eq = 1'b0;
  lt = 1'b0;
  gt = 1'b1;
 end
 else
 begin
  eq = 1'b0;
  lt = 1'b1;
  gt = 1'b0;
 end
end 
endmodule
```

OUTPUT WAVEFORM:

![image](https://github.com/Tarunkola1/VLSI-LAB-EXP-2/assets/161431337/c4d3c51a-4b74-4b53-84de-796a11c0f6e6)

RESULT:
THUS THE SIMULATION AND SYNTHESIS OF ENCODER, DECODER, MULTIPLEXER ,DE MULTIPLEXER,2BIT MAGNITUDE COMPARATOR USING VIVADO IS COMPLETED.
