library ieee;
use ieee.std_logic_1164.all;

entity test_multiplier is
end test_multiplier;

architecture behavior of test_multiplier is
    signal a, b: std_logic_vector(7 downto 0);
    signal unsigned_product, signed_product: std_logic_vector(15 downto 0);
    
    component unsigned_multiplier
        port (
            a, b: in std_logic_vector(7 downto 0);
            product: out std_logic_vector(15 downto 0)
        );
    end component;
    
    component signed_multiplier
        port (
            a, b: in std_logic_vector(7 downto 0);
            product: out std_logic_vector(15 downto 0)
        );
    end component;

begin
    U1: unsigned_multiplier port map (a, b, unsigned_product);
    U2: signed_multiplier port map (a, b, signed_product);

    process
    begin
        -- تست برای ورودی‌های مختلف
        a <= "00000001"; b <= "00000001"; wait for 10 ns; -- 1 * 1
        a <= "00000010"; b <= "00000010"; wait for 10 ns; -- 2 * 2
        a <= "00000101"; b <= "00000011"; wait for 10 ns; -- 5 * 3
        a <= "11111111"; b <= "00000001"; wait for 10 ns; -- 255 * 1
        a <= "10000000"; b <= "10000000"; wait for 10 ns; -- -128 * -128
        a <= "01111111"; b <= "11111111"; wait for 10 ns; -- 127 * -1

        wait; -- پایان شبیه‌سازی
    end process;
end behavior;
