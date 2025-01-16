library ieee;
use ieee.std_logic_1164.all;
use ieee.std_logic_signed.all;

entity signed_multiplier is
    port (
        a, b: in std_logic_vector(7 downto 0);
        product: out std_logic_vector(15 downto 0)
    );
end signed_multiplier;

architecture behavior of signed_multiplier is
begin
    product <= std_logic_vector(signed(a) * signed(b));
end behavior;
