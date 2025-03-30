# *HUFFMAN AND SHANNON-FANO CODING*  

## *Problem Statement:*  
Consider a discrete memoryless source with symbols and probabilities:  
*{0.125, 0.0625, 0.25, 0.0625, 0.125, 0.125, 0.25}*  
Apply Huffman and Shannon-Fano coding to this source.  

## *AIM:*  
To compute the *Average Codeword Length, Entropy, Efficiency, Redundancy, and Variance* for a discrete memoryless source using *Huffman and Shannon-Fano coding* based on the given probabilities and codeword lengths.  

## *TOOLS REQUIRED:*  
- *Python*: A versatile language for scientific computing and signal processing.  
- *NumPy & Matplotlib*: Libraries for numerical operations and high-quality visualizations, essential for demonstrating sampling.  

---

## *PROGRAM:*  
python
import numpy as np
import math

L = 0  # Average Codeword Length
hs = 0  # Entropy
p = []  # Probability list
lk = []  # Codeword length list

n = int(input("Enter the number of samples: "))

for i in range(n):
    pr = float(input(f"Enter the probability of sample {i + 1}: "))  
    p.append(pr)

for j in range(n):
    l = float(input(f"Enter the length of the sample {j + 1}: "))  
    lk.append(l)

# Compute Average Codeword Length
for k in range(n):
    L += p[k] * lk[k]

# Compute Entropy
for k in range(n):
    hs += p[k] * math.log2(1 / p[k])
hs = round(hs, 3)

# Compute Efficiency and Redundancy
eff = round(hs / L, 3)
red = round(1 - eff, 3)

# Compute Variance
var = 0
for k in range(n):
    var += p[k] * (lk[k] - L) ** 2
var = round(var, 3)

print()
print(f"Average Codeword Length: {L}")
print(f"Entropy: {hs}")
print(f"Efficiency: {eff * 100} %")
print(f"Redundancy: {red}")
print(f"Variance: {var}")


---

## *OUTPUT:*  
![Screenshot 2025-03-25 191943](https://github.com/user-attachments/assets/efa46457-a3cc-4c5a-b3c2-4795c1ed616c)  

---

## *CALCULATIONS:*  
![calculation](![image](https://github.com/user-attachments/assets/697c31ff-74c8-4ca0-95b0-8956f9625fd4)
)  
![calculations2](![image](https://github.com/user-attachments/assets/664e84c0-b49f-4f6b-b4ee-c3fbdefbfd5a)
) 
![calculations3](![image](https://github.com/user-attachments/assets/fa5d149b-dde1-438d-8c3c-243ebdcb6179)

) 

---

## *RESULT:*  
For the given probabilities *{0.125, 0.0625, 0.25, 0.0625, 0.125, 0.125, 0.25}*, the computed values are:  
- *Average Codeword Length: **2.625*  
- *Entropy: **2.625*  
- *Efficiency: **100.0%*  
- *Redundancy: **0.0*  
- *Variance: **0.484*
