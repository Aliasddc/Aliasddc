library IEEE;
use IEEE.std_logic_1164.all;

entity TB_BCD7Seg is
end entity TB_BCD7Seg;

architecture Behavioral of TB_BCD7Seg is

    component BCD7Seg is
        Port (
            x, y, z, w : in  std_logic;
            a, b, c, d, e, f, g : out std_logic
        );
    end component;

    signal x_sig, y_sig, z_sig, w_sig : std_logic;
    signal a_sig, b_sig, c_sig, d_sig, e_sig, f_sig, g_sig : std_logic;

begin

    uut: BCD7Seg 
        port map (
            x => x_sig, y => y_sig, z => z_sig, w => w_sig,
            a => a_sig, b => b_sig, c => c_sig, d => d_sig, e => e_sig, f => f_sig, g => g_sig
        );

    process
    begin
        -- Test case for 0
        x_sig <= '0'; y_sig <= '0'; z_sig <= '0'; w_sig <= '0'; 
        wait for 10 ns; 

        -- Test case for 1
        x_sig <= '0'; y_sig <= '0'; z_sig <= '0'; w_sig <= '1'; 
        wait for 10 ns; 

        -- ... Add test cases for other numbers (2-9) ...

        -- Test case for invalid input
        x_sig <= '1'; y_sig <= '1'; z_sig <= '1'; w_sig <= '1'; 
        wait for 10 ns; 

        wait; 
    end process;

end architecture Behavioral;
