library ieee;
use IEEE.std_logic_1164.all;

entity TB_BCD7Seg is
end TB_BCD7Seg;

architecture behavior of TB_BCD7Seg is

    signal x, y, z, w: std_logic := '0';
    signal a, b, c, d, e, f, g: std_logic;

    component BCD7Seg
        port (
            x, y, z, w: in std_logic;
            a, b, c, d, e, f, g: out std_logic
        );
    end component;

begin

    uut: BCD7Seg port map (
        x => x,
        y => y,
        z => z,
        w => w,
        a => a,
        b => b,
        c => c,
        d => d,
        e => e,
        f => f,
        g => g
    );

    process
    begin
        -- Test input 0
        x <= '0'; y <= '0'; z <= '0'; w <= '0';
        wait for 10 ns;

        -- Test input 1
        x <= '0'; y <= '0'; z <= '0'; w <= '1';
        wait for 10 ns;

        -- Test input 2
        x <= '0'; y <= '0'; z <= '1'; w <= '0';
        wait for 10 ns;

        -- Test input 3
        x <= '0'; y <= '0'; z <= '1'; w <= '1';
        wait for 10 ns;

        -- Test input 4
        x <= '0'; y <= '1'; z <= '0'; w <= '0';
        wait for 10 ns;

        -- Test input 5
        x <= '0'; y <= '1'; z <= '0'; w <= '1';
        wait for 10 ns;

        -- Test input 6
        x <= '0'; y <= '1'; z <= '1'; w <= '0';
        wait for 10 ns;

        -- Test input 7
        x <= '0'; y <= '1'; z <= '1'; w <= '1';
        wait for 10 ns;

        -- Test input 8
        x <= '1'; y <= '0'; z <= '0'; w <= '0';
        wait for 10 ns;

        -- Test input 9
        x <= '1'; y <= '0'; z <= '0'; w <= '1';
        wait for 10 ns;

        -- End simulation
        wait;
    end process;

end behavior;
