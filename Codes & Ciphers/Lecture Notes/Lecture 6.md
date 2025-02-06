**Name:** Stanley Goodwin
**Date:** 2/3/2025

---
## Vigenère Cipher
### Historical
It is a polyalphabetic cipher (multiple substitution alphabets).
### How it works
Key is repeated as many time to match the size of the plaintext.
The local shift from the key is applied to the plaintext character.
### Mathematical Definition
Let $K$ be the list of the key, and $M$ be the list of the plaintext.
Then the mapping is defined as the following:
$$C_i=E_K(M_i)=M_i+K_i\mod26$$
The decrypting function is given by:
$$M_i=D_K(C_i)=C_i-K_i\mod26$$

### Attacking
If the same word appears at a multiple of the length of the key apart, the ciphertext will be identical, and so can be exploited to find what the plaintext could have been.
### Friedman's Coincidence Index
If we pick 2 letters at random from the cipher text, what's the probability that they're the same?
$$p(\text{two letters are the same})=\sum_i^{26}\dfrac{N_i(N_i-1)}{N(N-1)}$$
### Coincidence Index with Vigenère
Let the key length be $k$. What is the probability that two letters are the same letter.

**Case 1:** The two letters match because they have matching plaintext and key values.
$$p(\text{Case 1})\approx\dfrac{1}{k}I_E$$
**Case 2:** The two letters match at random.
$$p(\text{Case 2})\approx\left(1-\dfrac{1}{k}\right)I_R$$
So the probability that two letters match is:
$$p(\text{2 letters match})\approx\dfrac{1}{k}I_E+\left(1-\dfrac{1}{k}\right)I_R$$
We can use this to estimate the length of the key word with:
$$k\approx\dfrac{I_E-I_R}{I_C-I_R}$$
If it's closest to $1$, it's likely just a shift cipher, but this is not a guarantee.
An issue that appears is that if there's a repeating letter in the key word, this calculation can get messed up because it tell you likely how many unique letters they are in the key.