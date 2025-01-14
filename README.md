library IEEE;
use IEEE.std_logic_1164.all;

entity MUX41 is
    port (
        S: in std_logic_vector(1 downto 0);
        A, B, C, D: in std_logic;
        Y: out std_logic
    );
end MUX41;

architecture bhv of MUX41 is
begin
    with S select
        Y <= A when "00",
             B when "01",
             C when "10",
             D when "11",
             'Z' when others;
end bhv;
