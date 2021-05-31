----------------------------------------------------------------------------------
-- Company: 
-- Engineer: 
-- 
-- Create Date: 28.05.2021 23:54:41
-- Design Name: 
-- Module Name: four_bit_comparator - Behavioral
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

entity four_bit_comparator is
  Port (y1, y2: in std_logic_vector (3 downto 0); Oeq: out std_logic );
end four_bit_comparator;

architecture Behavioral of four_bit_comparator is
signal f1, f2: std_logic;

begin
bit_pair_1: entity work.two_bit_comparator(Behavioral)
port map(v1(1)=> y1(3), v1(0)=>y1(2), v2(1)=> y2(3), v2(0)=> y2(2), Oeqb=> f1);
bit_pair_2: entity work.two_bit_comparator(Behavioral)
port map(v1(1)=> y1(1), v1(0)=>y1(0), v2(1)=> y2(1), v2(0)=> y2(0), Oeqb=> f2);

Oeq <= f1 or (f2 and ((y1(3) xnor y2(3)) and (y1(2) xnor y2(2))));
end Behavioral;
