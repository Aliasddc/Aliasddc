library ieee;
use IEEE.std_logic_1164.all;

entity BCD7Seg is
port (x,y,z,w: in std_logic;
a,b,c,d,e,f,g: out std_logic);
end BCD7Seg;

architecture TrTbl of BCD75eg is
signal INP: std_logic_vector(3 downto 0);
signal OUTP:std_logic_vector(6 downto 0);
begin
INP <= (x,y,z,w);
(a,b,c,d,e,f,g) <= OUTP;
with INP select
OUTP <=
"1111110" when "0000",
"0110000" when "0001",
"1101101" when "0010",
"1111001" when "0011",
"0110011" when "0100",
"1011011" when "0101",
"1011111" when "0110",
"1110000" when "0111",
"1111111" when "1000",
"1111011" when "1001",
"0000000" when others;
end TrTbl;
