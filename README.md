----------------------------------------------------------------------------------
-- Company: 
-- Engineer: 
-- 
-- Create Date: 27.05.2021 22:03:47
-- Design Name: 
-- Module Name: two_bit_comparator - Behavioral
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

entity two_bit_comparator is
-- to find v1 > v2
 Port (v1, v2: in std_logic_vector (1 downto 0); Oeqb: out std_logic );
end two_bit_comparator;

architecture Behavioral of two_bit_comparator is
signal e1, e2: std_logic;

begin
bit_1: entity work.one_bit_comparator(Behavioral)
port map(A=>v1(1), B=>v2(1), O=>e1);
bit_2: entity work.one_bit_comparator(Behavioral)
port map(A=>v1(0), B=>v2(0), O=>e2);

Oeqb <= e1 or (e2 and (v1(1) xnor v2(1)));

end Behavioral;
