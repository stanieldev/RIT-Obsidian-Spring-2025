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


https://mycourses.rit.edu/d2l/le/content/1133946/viewContent/10518026/View