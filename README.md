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
        -- Test all BCD inputs from 0 to 9
        for i in 0 to 9 loop
            x <= std_logic(to_unsigned(i, 4))(3);
            y <= std_logic(to_unsigned(i, 4))(2);
            z <= std_logic(to_unsigned(i, 4))(1);
            w <= std_logic(to_unsigned(i, 4))(0);
            wait for 10 ns;  -- Wait for 10 ns for the output to stabilize
        end loop;

        -- End simulation
        wait;
    end process;

end behavior;
