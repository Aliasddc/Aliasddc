library IEEE;
use IEEE.STD_LOGIC_1164.ALL;

entity BCD_to_7seg is
    port(
        x, y, z, w: in STD_LOGIC;
        a, b, c, d, e, f, g: out STD_LOGIC
    );
end entity BCD_to_7seg;

architecture Behavioral of BCD_to_7seg is
begin
    process(x, y, z, w)
    begin
        case (x & y & z & w) is
            when "0000" => -- 0
                a <= '1'; b <= '1'; c <= '1'; d <= '1'; e <= '1'; f <= '1'; g <= '0';
            when "0001" => -- 1
                a <= '0'; b <= '1'; c <= '1'; d <= '0'; e <= '0'; f <= '0'; g <= '0';
            when "0010" => -- 2
                a <= '1'; b <= '1'; c <= '0'; d <= '1'; e <= '1'; f <= '0'; g <= '1';
            when "0011" => -- 3
                a <= '1'; b <= '1'; c <= '1'; d <= '1'; e <= '0'; f <= '0'; g <= '1';
            when "0100" => -- 4
                a <= '0'; b <= '1'; c <= '1'; d <= '0'; e <= '0'; f <= '1'; g <= '1';
            when "0101" => -- 5
                a <= '1'; b <= '0'; c <= '1'; d <= '1'; e <= '0'; f <= '1'; g <= '1';
            when "0110" => -- 6
                a <= '1'; b <= '0'; c <= '1'; d <= '1'; e <= '1'; f <= '1'; g <= '1';
            when "0111" => -- 7
                a <= '1'; b <= '1'; c <= '1'; d <= '0'; e <= '0'; f <= '0'; g <= '0';
            when "1000" => -- 8
                a <= '1'; b <= '1'; c <= '1'; d <= '1'; e <= '1'; f <= '1'; g <= '1';
            when "1001" => -- 9
                a <= '1'; b <= '1'; c <= '1'; d <= '1'; e <= '0'; f <= '1'; g <= '1';
            when others =>
                -- در صورتی که ورودی نامعتبر باشد، همه خروجی‌ها را صفر کنید.
                a <= '0'; b <= '0'; c <= '0'; d <= '0'; e <= '0'; f <= '0'; g <= '0';
        end case;
    end process;
end architecture Behavioral;
