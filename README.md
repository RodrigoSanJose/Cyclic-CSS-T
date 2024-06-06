# CSS-T codes from cyclic codes

This is the repository for the codes obtained in the paper "E. Camps-Moreno, H.H. López, G.L. Matthews, D. Ruano, R. San-José, I. Soprunov. An algebraic characterization of binary CSS-T codes and cyclic CSS-T codes for quantum fault tolerance. Quantum Inf Process 23, 230 (2024)".
DOI: https://doi.org/10.1007/s11128-024-04427-5

## Files 

For a given  CSS-T code with parameters [[n,k,d]], the zip archive Matrices.zip contains a parity check matrix for C1 in the files "n_k_d_C1.txt" and "n_k_d_C1.npy". Similarly for C2.

-The .txt files contain in the first line the cyclotomic sets used to construct the (extended) cyclic codes (resp. the degree for Reed-Muller codes), and the parity check matrix in plain text. For non-extended cyclic codes, we use 0 instead of n for the cyclotomic sets (with respect to the paper).

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
