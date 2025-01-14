library IEEE;
use IEEE.std_logic_1164.all;

entity tb_MUX41 is
end tb_MUX41;

architecture behavior of tb_MUX41 is
    signal S: std_logic_vector(1 downto 0);
    signal A, B, C, D: std_logic;
    signal Y: std_logic;

    component MUX41 is
        port (
            S: in std_logic_vector(1 downto 0);
            A, B, C, D: in std_logic;
            Y: out std_logic
        );
    end component;

begin
    uut: MUX41 port map (
        S => S,
        A => A,
        B => B,
        C => C,
        D => D,
        Y => Y
    );

    -- Stimulus process
    stim_proc: process
    begin
        -- Test case 1
        A <= '0'; B <= '0'; C <= '0'; D <= '0'; S <= "00"; wait for 10 ns;
        assert (Y = '0') report "Test case 1 failed" severity error;

        -- Test case 2
        A <= '0'; B <= '1'; C <= '0'; D <= '0'; S <= "01"; wait for 10 ns;
        assert (Y = '1') report "Test case 2 failed" severity error;

        -- Test case 3
        A <= '0'; B <= '0'; C <= '1'; D <= '0'; S <= "10"; wait for 10 ns;
        assert (Y = '1') report "Test case 3 failed" severity error;

        -- Test case 4
        A <= '0'; B <= '0'; C <= '0'; D <= '1'; S <= "11"; wait for 10 ns;
        assert (Y = '1') report "Test case 4 failed" severity error;

        -- Test case 5 (Invalid case)
        A <= '0'; B <= '0'; C <= '0'; D <= '0'; S <= "XX"; wait for 10 ns;
        assert (Y = 'Z') report "Test case 5 failed" severity error;

        wait;
    end process stim_proc;

end behavior;
