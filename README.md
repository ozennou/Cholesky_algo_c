# Cholesky Factorization

[![License](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)


## Overview

This repository provides an implementation of the Cholesky factorization, a decomposition method used to factorize a Hermitian, positive-definite matrix into the product of a lower triangular matrix and its conjugate transpose.

## Methodology

The Cholesky factorization computes a lower triangular matrix L such that A = LL^H, where A is a Hermitian, positive-definite matrix and L^H denotes the conjugate transpose of L.

The factorization is computed through a two-step process:

1. **Cholesky Decomposition**: The matrix A is decomposed into L by performing a sequence of computations that exploit the symmetry and positive-definiteness of A. The elements of L are obtained by applying specific formulas:
 ```
      L(i, i) = sqrt(A(i, i) - Σ(L(i, k)^2)), for k = 1 to i-1
      L(j, i) = (A(j, i) - Σ(L(i, k) * L(j, k))), for j > i
```
3. **Back Substitution**: Once L is obtained, it can be used to efficiently solve linear systems of equations of the form LL^Hx = b, where b is the right-hand side vector and x is the solution vector. Back substitution algorithm is used to obtain the solution x.

## Properties and Applications

The Cholesky factorization has several properties and applications:

- It is more computationally efficient than other matrix factorization methods, such as LU decomposition, for solving linear systems with symmetric positive-definite matrices.
- The factorization is unique for positive-definite matrices, allowing for efficient and accurate solutions to systems of equations.
- It is used in various numerical algorithms, including optimization methods, least squares fitting, and simulation techniques.
- The Cholesky factorization is numerically stable and avoids the numerical instability associated with direct matrix inversion.

