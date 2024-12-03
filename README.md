library IEEE;
use IEEE.STD_LOGIC_1164.ALL;

entity MUX4to1_tb is
end MUX4to1_tb;

architecture Behavioral of MUX4to1_tb is

    signal A : STD_LOGIC := '0';
    signal B : STD_LOGIC := '0';
    signal C : STD_LOGIC := '0';
    signal D : STD_LOGIC := '0';
    signal S : STD_LOGIC_VECTOR(1 downto 0) := "00";
    signal Y : STD_LOGIC;

    -- Instantiate the Unit Under Test (UUT)
    component MUX4to1
        Port ( A : in STD_LOGIC;
               B : in STD_LOGIC;
               C : in STD_LOGIC;
               D : in STD_LOGIC;
               S : in STD_LOGIC_VECTOR(1 downto 0);
               Y : out STD_LOGIC);
    end component;

begin

    UUT: MUX4to1
        Port map (
            A => A,
            B => B,
            C => C,
            D => D,
            S => S,
            Y => Y
        );

    -- Test process
    stimulus: process
    begin
        -- Test case 1
        A <= '1'; B <= '0'; C <= '0'; D <= '0'; S <= "00";
        wait for 10 ns;
        
        -- Test case 2
        A <= '0'; B <= '1'; C <= '0'; D <= '0'; S <= "01";
        wait for 10 ns;
        
        -- Test case 3
        A <= '0'; B <= '0'; C <= '1'; D <= '0'; S <= "10";
        wait for 10 ns;
        
        -- Test case 4
        A <= '0'; B <= '0'; C <= '0'; D <= '1'; S <= "11";
        wait for 10 ns;

        -- Test case 5: Check with all inputs
        A <= '1'; B <= '1'; C <= '1'; D <= '1'; S <= "00";
        wait for 10 ns;
        S <= "01"; wait for 10 ns;
        S <= "10"; wait for 10 ns;
        S <= "11"; wait for 10 ns;

        -- Finish simulation
        wait;
    end process;

end Behavioral;
