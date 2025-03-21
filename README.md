# cs2810-lab5

A simple description (had to turn this in with the lab):

## Part A

0001010000000001 - ADD R0 + R1 and store in R2
Breakdown:
0001 – OPcode for ADD
010 – DR = R2
000 – SR1 = R0 (addend one)
0 – Defines second addend to be from a register instead of an immediate add
00 – filler 0s
001 – SR2 = R1 (addend two)

0010010110110101 – LD R2 into PC + Offset 
Breakdown:
0010 – OPcode for LD
010 – DR = R2
110110101 = Offset = -75 Decimal = -4B Hex

1111000000001101 – TRAP x0D
Breakdown:
1111 – OPcode for TRAP
0000 – Filler 0s
00001101 – TRAP vector

## Part B

This is meant to be a subtractor for two numbers stored in the two memory slots immediately before the initial instruction (based on PC).
1110001111111101 – LEA R1, Offset - 2
Set R1 to M[PC - 2]
1110010111111101 – LEA R2, Offset - 2
Set R2 to M[PC - 2]
1001010010111111 – NOT R2, R2
Set R2 to NOT R2
0001010010100001 – ADD R2, R2, 1
Add 1 to R2 and store it in R2
0001011001000010 – ADD R3, R1, R2
Add R1 to R2 and store in R3
