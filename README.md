library ieee;
use ieee.std_logic_1164.all;
use ieee.std_logic_unsigned.all;

entity unsigned_multiplier is
    port (
        a, b: in std_logic_vector(7 downto 0);
        product: out std_logic_vector(15 downto 0)
    );
end unsigned_multiplier;

architecture behavior of unsigned_multiplier is
begin
    product <= a * b;
end behavior;
