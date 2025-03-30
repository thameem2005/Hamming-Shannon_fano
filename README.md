# HUFFMAN AND SHANNON-FANO 
## Consider a discrete memoryless source with symbols and statistics {0.125, 0.0625, 0.25, 0.0625, 0.125, 0.125, 0.25} for its output.
## Apply the Huffman and Shannon-Fano to this source.
## Show that draw the tree diagram, the average code word length, Entropy, Variance, Redundancy, Efficiency.
## GANAPATHY SHRIRAM V B 
## 212223060064
## Aim
To compute the Average Codeword Length, Entropy, Efficiency, Redundancy, and Variance for a discrete memoryless source using Huffman and Shannon-Fano coding based on the given probabilities and codeword lengths.
## Tools Required
Python: A versatile programming language used for scientific computing and signal processing. NumPy: A powerful numerical library in Python for performing array-based operations and mathematical computations. Matplotlib: A plotting library for generating high-quality graphs and visualizations of data, essentialfor demonstrating the sampling process.
## Program
```
import numpy as np
import math 
L  = 0
hs = 0
p = []
lk = []
n = int(input("Enter the number of Samples : "))
for i in range (n): 
    pr = float(input(f"Enter the probability of sample values {i + 1}: "))  
    p.append(pr)
for j in range (n): 
    l = float(input(f"Enter the length of the sample values {j + 1}: "))  
    lk.append(l)

for k in range (n):
    Avg1 = p[k] * lk[k]
    L = L + Avg1

for k in range (n):
    e = p[k] * math.log(1 / p[k], 2)
    hs = hs + e
hs = round(hs,3)

eff = hs / L
eff = round(eff,3)

red =  round(1 - eff,3) 

var = 0
for k in range(n):
    var1 = p[k] * (lk[k]-L)**2
    var = var + var1
var = round(var,3)
print()
print(f"Average Codeword Length is : {L}")
print(f"Entropy is : {hs}")
print(f"Efficiency is : {eff*100} %")
print(f"Redudancy is : {red}")
print(f"Variance is : {var}")
```
## OUTPUT
![image](https://github.com/user-attachments/assets/58527e36-3940-462e-83ea-6479cc66b775)
## Calculation
![WhatsApp Image 2025-03-30 at 13 43 12_b2c08247](https://github.com/user-attachments/assets/f53f7a58-b1e3-411e-80b7-d751de6b4dc2)
![WhatsApp Image 2025-03-30 at 13 43 12_78998309](https://github.com/user-attachments/assets/e1b082cc-41c1-4f00-abc4-e340af423156)
![WhatsApp Image 2025-03-30 at 13 43 12_e1473b4f](https://github.com/user-attachments/assets/d078a633-56dd-44c0-b113-f49e6c369949)




## Results
For the given probabilities 0.125,0.0625,0.25,0.0625,0.125,0.125,0.25
Average Codeword Length is : 2.625 Entropy is : 2.625 Efficiency is : 100.0 % Redudancy is : 0.0 Variance is : 0.484
