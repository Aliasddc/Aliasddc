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
                -- ... (بقیه موارد را به همین ترتیب بنویسید)
            -- ...
            when others =>
                -- در صورتی که ورودی نامعتبر باشد، همه خروجی‌ها را صفر کنید.
                a <= '0'; b <= '0'; c <= '0'; d <= '0'; e <= '0'; f <= '0'; g <= '0';
        end case;
    end process;
end architecture Behavioral;
