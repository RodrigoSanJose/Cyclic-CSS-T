# CSS-T codes from cyclic codes

This is the repository for the codes obtained in the paper "E. Camps-Moreno, H.H. López, G.L. Matthews, D. Ruano, R. San-José, I. Soprunov. The poset of binary CSS-T quantum codes and cyclic codes. ArXiv 2312.17518 (2023)".
DOI: https://doi.org/10.48550/arXiv.2312.17518

## Files 

The parity check matrix for C1 of the code [n,k,d] is saved in the file with name "n_k_d_C1.txt" and "n_k_d_C1.npy". Similarly for C2.

-The .txt files contain in the first line the cyclotomic sets used to construct the (extended) cyclid codes (resp. the degree for Reed-Muller codes), and the parity check matrix in plain text. For non-extended cyclic codes, we use 0 instead of n for the cyclotomic sets (with respect to the paper).

-The .npy files contain the parity check matrix in binary format. We provide below an example to load this matrix with Python and SageMath.

## Example to load the matrices for the code [[32,4,4]]
### Python:

import numpy

H1=numpy.load('32_4_4_C1.npy')

H2=numpy.load('32_4_4_C2.npy')

#### (H1 and H2 are the parity check matrices of C1 and C2 in numpy array format)

### SageMath

import numpy

A1=numpy.load('32_4_4_C1.npy')

A2=numpy.load('32_4_4_C2.npy')

H1=matrix(GF(2),A1)

H2=matrix(GF(2),A2)

C1=LinearCode(H1).dual_code()

C2=LinearCode(H2).dual_code()
