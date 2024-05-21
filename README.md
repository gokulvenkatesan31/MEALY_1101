# MEALY_1101
![image](https://github.com/RESMIRNAIR/MEALY_1101/assets/154305926/fce7c9dc-e0df-4528-843b-559bf24f018a)
# Program
```
module mealy1101 (x,z,clk,rst);

input x,clk,rst;

output reg z;

parameter s0=2'b00,s1=2'b01,s2=2'b10,s3=2'b11;

reg[1:0] PS,NS;

always@(posedge clk or posedge rst)

begin

if (rst)

PS<=s0;

else

PS<=NS;

end

always@(PS or x)

begin

case(PS)

s0: begin

z=0;

NS=x?s1:s0;

end

s1: begin

z=0;

NS=x?s2:s0;

end

s2: begin

z=0;

NS=x?s2:s3;

end

s3: begin

z=x?1:0;

NS=x?s1:s0;

end

endcase

end

endmodule
```
# Output

![329981487-aad9962d-036c-4dc5-a221-e9ab6a590dba](https://github.com/gokulvenkatesan31/MEALY_1101/assets/123715763/5b06ad40-73e9-4429-84c5-62285819841c)
