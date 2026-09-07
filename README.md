# 3-bit-nand-memory

3-bit hardware memory built from NAND RS latches with a Karnaugh-map-optimized 2-out-of-3 majority voter and RGB LED output.
The result is shown with an RGB LED:
Red — output 0
Green — output 1


SCHEME:
![scheme](SCHEME.jpg)

--------------------------------------------------------------------------------------------------------------------------------
## |3-bit memory|

The main part of the project is a 3-bit memory built from three asynchronous RS latches.

Each latch stores one bit:

RS latch A → bit A

RS latch B → bit B

RS latch C → bit C

The feedback inside each NAND latch keeps the selected state after the push button is released.



RS LATCH SCHEME:


![RS scheme](RS_scheme.jpg)

--------------------------------------------------------------------------------------------------------------------------------
## |Majority voting logic|
The output is HIGH when at least two of the three stored bits are HIGH.

The function was simplified using a Karnaugh map:
Y = AB + AC + BC

Then it was transformed using De Morgan's law for a NAND-only implementation

CALCULATIONS:


![calculations](CALCULATIONS.png)

--------------------------------------------------------------------------------------------------------------------------------- 
## Total NAND gate count

3 RS latches × 2 NAND gates = 6 NAND gates

majority voter = 6 NAND gates

Total: 12 two-input NAND gates
--------------------------------------------------------------------------------------------------------------------------------- 
The circuit was then assembled as a real hardware prototype using logic ICs, push buttons, resistors, wiring, and an RGB LED.

FINAL HARDWARE PROTOTYPE:
![FINAL HARDWARE PROTOTYPE](assembled_circuit_1.jpeg)
![FINAL HARDWARE PROTOTYPE](assembled_circuit_2.jpeg)

ASSEMBLED CIRCUIT IN TWO STATES OUT = 1/0:
![STATES 0/1](RGB_LED_output_states.png)

--------------------------------------------------------------------------------------------------------------------------------- 
