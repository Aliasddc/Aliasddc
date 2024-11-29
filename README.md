library IEEE;
use IEEE.STD_LOGIC_1164.ALL;

entity tb_mux_4to1 is
end tb_mux_4to1;

architecture Behavioral of tb_mux_4to1 is
    signal A, B, C, D : STD_LOGIC := '0';
    signal S : STD_LOGIC_VECTOR(1 downto 0) := "00";
    signal Y : STD_LOGIC;

    component mux_4to1 is
        Port (
            A : in STD_LOGIC;
            B : in STD_LOGIC;
            C : in STD_LOGIC;
            D : in STD_LOGIC;
            S : in STD_LOGIC_VECTOR(1 downto 0);
            Y : out STD_LOGIC
        );
    end component;

begin
    uut: mux_4to1 Port Map (A => A, B => B, C => C, D => D, S => S, Y => Y);

    process
    begin
        -- آزمون 1
        A <= '1'; B <= '0'; C <= '0'; D <= '0'; S <= "00"; wait for 10 ns;
        -- آزمون 2
        A <= '0'; B <= '1'; C <= '0'; D <= '0'; S <= "01"; wait for 10 ns;
        -- آزمون 3
        A <= '0'; B <= '0'; C <= '1'; D <= '0'; S <= "10"; wait for 10 ns;
        -- آزمون 4
        A <= '0'; B <= '0'; C <= '0'; D <= '1'; S <= "11"; wait for 10 ns;

        wait;
    end process;
end Behavioral;
