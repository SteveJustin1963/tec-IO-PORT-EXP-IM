# tec-IO-PORT-EXP-IM
TEC-1 32 Port Select Expansion daughter board

![](https://github.com/SteveJustin1963/tec-IO-PORT-EXP-IM/blob/main/pics/cct1.png)

Ian McLean has proposed a circuit for expanding the number of ports on a TEC-1 daughter board from 8 to 32. He plans to use 138 decoders and 1/2 of a 139 decoder to achieve this. The purpose of the expansion is to allow for the construction of a 16x8 LED display (or larger) with every LED individually addressable and latch-able, eliminating the need for multiplexing.

Paul Antoine suggests using a CPLD for the project, and Mark Jelic agrees that this would be a good learning opportunity. However, Jelic points out that such a large display would be quite expensive to build.

Andrew McMeikan suggests using a shift register to control the LEDs, which would be easier to expand than using latches.

