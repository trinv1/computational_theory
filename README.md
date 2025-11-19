# Computational Theory

## Introduction 
This project covers the computational concepts that support the [Secure Hash Standard](https://nvlpubs.nist.gov/nistpubs/FIPS/NIST.FIPS.180-4.pdf), in particular the SHA-256 hashing algorithm. This notebook aims to explore the various computational and mathematical operations that are involved in cryptographic systems. 
Each problem focuses on a different stage of the SHA-256 process, from bitwise operations to generating constants and performing hashing computations.

## Requirements
This project requires the following Python packages:<br>
* **numpy**<br>

### To install these dependencies:
**pip install -r requirements.txt**

## Overview 
### Problem 1
#### Binary Words and Operations
In Problem 1, we are implementing the SHA-256 logical functions (Parity, Ch, Maj, Σ₀, Σ₁, σ₀, σ₁) using NumPy to perform 32-bit operations. SHA-256 operates through these logical functions and bitwise operations, providing a high level of security that is resistant to collisions and **pre-image attacks** (original message before its been hashed) ([SHA-256 logical functions explanation](https://mojoauth.com/compare-hashing-algorithms/sha-256-vs-sha-384/)).

### Problem 2
#### Fraction Parts of Cube Roots
In Problem 2, we are generating the first 64 prime numbers using The Sieve of Eratosthenes Algorithm for speed and memory efficiency, and computing the SHA-256 constants from the fractional parts of their cube roots. These constants are mathematically derived values defined by the Secure Hash Standard to ensure non-linearity and to prevent predictable patterns in the hash process, ensuring that each round of the computation is different. 

### Problem 3 



