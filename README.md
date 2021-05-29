# IITB-SSP-mini

----------------------------------------------------------------------------------
-- Company: 
-- Engineer: 
-- 
-- Create Date: 27.05.2021 23:27:54
-- Design Name: 
-- Module Name: one_bit_comparator_TB - Behavioral
-- Project Name: 
-- Target Devices: 
-- Tool Versions: 
-- Description: 
-- 
-- Dependencies: 
-- 
-- Revision:
-- Revision 0.01 - File Created
-- Additional Comments:
-- 
----------------------------------------------------------------------------------


library IEEE;
use IEEE.STD_LOGIC_1164.ALL;

-- Uncomment the following library declaration if using
-- arithmetic functions with Signed or Unsigned values
--use IEEE.NUMERIC_STD.ALL;

-- Uncomment the following library declaration if instantiating
-- any Xilinx leaf cells in this code.
--library UNISIM;
--use UNISIM.VComponents.all;

entity one_bit_comparator_TB is
--  Port ( );
end one_bit_comparator_TB;

architecture Behavioral of one_bit_comparator_TB is
signal testA, testB: std_logic;
signal testO: std_logic;
begin
uut: entity work.one_bit_comparator(Behavioral)
port map(A=>testA, B=>testB, O=>testO);
process 
begin
testA <= '0';
testB <= '0';
wait for 20ps;

testA <= '0';
testB <= '1';
wait for 20ps;

testA <= '1';
testB <= '0';
wait for 20ps;

testA <= '1';
testB <= '1';
wait for 20ps;
end process;

end Behavioral;
