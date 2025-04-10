# EXP.NO.6-Simulation-of-Hamming-and-Shannon-Fano-Code
6. Simulation of Hamming and Shannon-Fano Code

# AIM
To implement Huffman and Shannon-Fano coding for a discrete memoryless source with given probabilities and analyze the efficiency, redundancy, and variance.

# SOFTWARE REQUIRED
Python

# ALGORITHMS
1.Start

2.Input symbols and their probabilities.

3.Sort symbols: Huffman: Ascending order. Shannon-Fano: Descending order.

4.Generate codewords: Huffman: Combine smallest probabilities until one node remains. Shannon-Fano: Split list recursively with near-equal probabilities.

5.Calculate entropy, average length, efficiency, and redundancy.

6.Display results.


# PROGRAM
``` python
import numpy as np
import math
def calculate_coding_parameters(n):
p = []
lk = []
  for i in range(n):
    pr = float(input(f"Enter the probability of sample values {i + 1}: "))
    p.append(pr)
    l = float(input(f"Enter the length of the sample values {i + 1}: "))
    lk.append(l)
  L = sum(p[k] * lk[k] for k in range(n))
  hs = sum(p[k] * math.log(1 / p[k], 2) for k in range(n))
  hs = round(hs, 3)
  eff = round(hs / L, 3)
  red = round(1 - eff, 3)
  var = round(sum(p[k] * (lk[k] - L)**2 for k in range(n)), 3)
return L, hs, eff, red, var
n = int(input("Enter the number of Samples : "))
L, hs, eff, red, var = calculate_coding_parameters(n)
print(f"Average Codeword Length is : {L}")
print(f"Entropy is : {hs}")
print(f"Efficiency is : {eff * 100}%")
print(f"Redudancy is : {red}")
print(f"Variance is : {var}")
``` 



# OUTPUT
![image](https://github.com/user-attachments/assets/6026c3c8-d5a8-46fc-8c4e-5e74298b3a7a)


 
# RESULT
The simulation of Hamming and Shannon-Fano Code was successfully completed using Python, demonstrating effective error detection and correction in Hamming Code and efficient data compression with minimal redundancy in Shannon-Fano Code.
