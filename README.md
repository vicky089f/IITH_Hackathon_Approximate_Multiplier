# Approximate_Multiplier
Dadda multiplier using half adders, full adders, exact 4:2 compressors and approximate 4:2 compressors

## Abstract
Multiplication, a core operation in all digital signal processing algorithms, consumes a tremendous amount of power. But DSP applications are immune to a certain amount of error since human eyes have an inherent inability to detect such minor errors. This enables us to replace the exact computations with inexact computations, and by doing so it can be optimized to save area and power consumption for an unnoticeable drop in accuracy.

## Proposed Multiplier Architecture
The 8x8 unsigned Dadda-tree multiplier has been used for the approximate multiplier architecture. The Dadda-tree multiplier has three stages.
```
1. Parital Product Generation:
The two 8-bit inputs are ANDed using 2-bit AND gates to generate 64 partial products.

2. Partial Product Reduction:
The partial products are reduced to two rows using the half adders, full adders, exact 4:2 compressors and the proposed approximate 4:2 compressor.

3. Final Accumulation:
The last two rows are then added using an exact ripple carry adder to form the final product.
```
## Reference Circuit
In the reference circuit, the partial product reduction structure and the ripple carry adder stage are included, while the AND gates that form the partial product generation stage are omitted. The partial product rows have been divided into two parts: approximate part consisting of 8 columns, and exact part consisting of the remaining 7 columns. The approximaate part uses the proposed approximate compressors and half adders for reduction, whereas the exact part utilizes exact compressors, full adders and half adders for reduction.

![](https://github.com/vicky089f/Approximate_Multiplier/blob/main/Images/Xilin_Architecture.png)

## Tools Used
1. Synopsys Custom Compiler: For Circuit Design
2. Synopsys 28nm PDK
3. Synopsys PrimeWave: For simulations and viewing waveforms


## Proposed Approximate 4:2 Compressor
The approximate compressor is an arithmetic module that takes 4 inputs: X1, X2, X3, X4, and reduces it to give 2 outputs: Sum and Carry. It has been designed by introducing a few errors in the truth table, as shown below. The error distance of '-1' has been introduced for five cases, and the total probability of error of the compressor is 37/256.

![](https://github.com/vicky089f/Approximate_Multiplier/blob/main/Images/Approximate%20Compressor%20TT.png)

## Synopsys schematic for all the modules used
### CMOS Inverter
![CMON Inverter](https://github.com/vicky089f/Approximate_Multiplier/blob/main/Images/CMOS%20Inverter.png)

### CMOS NAND Gate
![](https://github.com/vicky089f/Approximate_Multiplier/blob/main/Images/CMOS%20NAND.png)

### CMOS NOR Gate
![](https://github.com/vicky089f/Approximate_Multiplier/blob/main/Images/CMOS%20NOR.png)

### CMOS XOR Gate
![](https://github.com/vicky089f/Approximate_Multiplier/blob/main/Images/CMOS%20XOR.png)

### CMOS AND Gate
![](https://github.com/vicky089f/Approximate_Multiplier/blob/main/Images/CMOS%20AND.png)

### CMOS OR Gate
![](https://github.com/vicky089f/Approximate_Multiplier/blob/main/Images/CMOS%20OR.png)

### Half Adder
![](https://github.com/vicky089f/Approximate_Multiplier/blob/main/Images/Half%20Adder.png)

### Full Adder
![](https://github.com/vicky089f/Approximate_Multiplier/blob/main/Images/Full%20Adder.png)

### Exact 4:2 Compressor
![](https://github.com/vicky089f/Approximate_Multiplier/blob/main/Images/Exact%20Compressor.png)

## Synopsys schematic of the modules proposed the authors in the paper

### Proposed NAND Gate
![](https://github.com/vicky089f/Approximate_Multiplier/blob/main/Images/Xilin%20NAND.png)

### Proposed XNOR Gate
![](https://github.com/vicky089f/Approximate_Multiplier/blob/main/Images/Xilin%20XNOR.png)

### Proposed approximate 4:2 compressor
![](https://github.com/vicky089f/Approximate_Multiplier/blob/main/Images/Xilin%20Approximate%20Compressor.png)

## Synopsys Schematic of the Approximate Multiplier
![](https://github.com/vicky089f/Approximate_Multiplier/blob/main/Images/Xilin%20Multiplier%20Architecture.png)

## Simulation
### Transient analysis
![](https://github.com/vicky089f/Approximate_Multiplier/blob/main/Images/Simulation.png)

### Input Waveforms
![](https://github.com/vicky089f/Approximate_Multiplier/blob/main/Images/Input%20Waveforms.png)

### Output Waveforms
![](https://github.com/vicky089f/Approximate_Multiplier/blob/main/Images/Output%20Waveforms.png)


## References
X. Yi, H. Pei, Z. Zhang, H. Zhou and Y. He, "Design of an Energy-Efficient Approximate Compressor for Error-Resilient Multiplications," 2019 IEEE International Symposium on Circuits and Systems (ISCAS), 2019, pp. 1-5, doi: 10.1109/ISCAS.2019.8702199.
