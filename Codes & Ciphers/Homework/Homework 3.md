**Name:** Stanley Goodwin
**Date:** 1/21/2025

---
### Problem 1
You receive the following cipher text (in standard blocks of 5 characters):
`SSEMA DPTLZ PTBHS JQBTY ARDYW HPX`
You are given the following collateral information:
 - The message was encrypted with a Vigenère cipher.
 - The keyword has length 4..
 - The keyword starts with letter W.
 - The word "the" appears at least once in the plaintext.
#### Problem 1.A
What was the plaintext? (Your answer should be given in readable English words.)
#### Problem 1.B
What was the keyword?
#### Problem 1.C
Write up a careful description of how you broke this, what techniques you used (including anything that didn’t work), and how you arrived at your answer.
#### Problem 1.D
If you’d had less collateral information, do you think you could have recovered the plaintext? Explain why, or why not. Include a description of the relative importance/value of each of the 4 pieces of collateral information.

---
### Problem 2
You receive the following cipher text (in standard blocks of 5 characters), which you believe has been encrypted with a Vigenère cipher:
`SMMPF YPTMO HJNFZ PNEKV FPLQP RBLEM YXXBT PABAR RYWWU SWBLQ WSQRM GZV`
You have a spy friend who tells you that they strongly suspect the plaintext starts with the phrase “hello friends”.
#### Problem 2.A
What was the complete plaintext? (Your answer should be given in readable English words.)
#### Problem 2.B
What was the keyword?
#### Problem 2.C
What do you conclude about the vulnerability of the Vigenère cipher to a “matched plaintext-ciphertext”-style cryptanalytic attack?

---
### Problem 3
You receive the following cipher text (in standard blocks of 5 characters) which you know is English text that was encrypted with a Vigenère cipher:
```
HJFMR VHLIL VSPTC JESIP PSOVO PBHWD IRHAS WWSOC MCHLI PIXYB BSJIV ICTOV AWSRX WSGPD IHWWI RKDDT VTGWM KSPCA CAMCH LIWSE ZTBWM WOHFT SRTPG WMCUE PDBIS CVSVH SFERY XLGCY KWOWM CUYPP FPCSF IEGMX VPQXS UQSYC HVCPB HEIZI RVHLJ DIRHB MWIAT EWIVI WWOHI HCJXW SIZTB MRVRV ILCRA XHLMC JMILC JXWSQ IAORG WCPCW CYWTC JYHVI V
```
Someone helpful also provided the following table of repeated strings (of length 4 or longer) that appear in the cipher text, along with the starting positions where they appear:

| Ciphertext | Starting Indices |
| ---------- | ---------------- |
| MCHLI      | 40, 92           |
| CJXWS      | 206, 234         |
| RVHL       | 4, 180           |
| DIRH       | 29, 185          |
| MCHL       | 40, 92           |
| CHLI       | 41, 93           |
| WMCU       | 115, 143         |
| CJXW       | 206, 234         |
| JXWS       | 207, 235         |
**Table 1:** Repeated Strings of 4 Characters
#### Problem 3.A
Find the length of the keyword that was used. Explain how you arrived at this answer and how confident you are that it is correct.
#### Problem 3.B
Determine the keyword that was used. Fully show or describe the work you did to arrive at this answer, and how confident you are that it is correct.
#### Problem 3.C
Decrypt the cipher text and recover the plain text, writing it in readable English sentences. (Make your best guess at punctuation, capitalization, and sentence structure.)
#### Problem 3.D
Compute the observed index of coincidence for the cipher text, and use it to “predict” the length of the keyword. How accurate is this prediction? Describe some of the limitations of using the index of coincidence.