**Name:** Stanley Goodwin
**Date:** 1/21/2025

---
### Problem 1
You receive the following cipher text (in standard blocks of 5 characters):
`SSEMA DPTLZ PTBHS JQBTY ARDYW HPX`
You are given the following collateral information:
 - The message was encrypted with a Vigenère cipher.
 - The keyword has length 4.
 - The keyword starts with letter W.
 - The word "the" appears at least once in the plaintext.
#### Problem 1.A
What was the plaintext? (Your answer should be given in readable English words.)
> we the people of the united states

---
#### Problem 1.B
What was the keyword?
> wolf

---
#### Problem 1.C
Write up a careful description of how you broke this, what techniques you used (including anything that didn’t work), and how you arrived at your answer.

**Line of Thinking**
Let $S$ be the set of all 26 letters of the alphabet.
1. The keyword has length 4 $\implies \text{key}\in S^4$.
2. The keyword starts with "W" $\implies \text{key}\in \text{"W"}\times S^3$.
3. The word "the" appears in the plaintext $\implies$ $\exists U\ |\ (\text{key}\in U) \ \land \ (U\subset \text{"W"}\times S^3)$
In English, we can reduce the set of possible keys with the 3 cases above.
Let $K$ be the set of all keys of any length greater than 1.

| Obs. | Cardinality of $K$ |
| ---- | ------------------ |
| 0    | $\|K\|=\infty$     |
| 1    | $\|K\|=26^4$       |
| 2    | $\|K\|=26^3$       |
| 3    | $\|K\|=58$         |
I used code to brute force through the keys to find the solutions that had the word "the" inside of the plaintext after decryption. 
```python
def decrypt(ciphertext: str, key: str):  
    plaintext = ""
    ciphertext = ciphertext.replace(" ", "")  
    for i, c in enumerate(ciphertext):  
        key_index = i % len(key)  
        key_char = key[key_index]  
        shift = LETTER_TO_NUMBER[key_char]  
        new_char = NUMBER_TO_LETTER[(LETTER_TO_NUMBER[c.lower()] - shift) % 26]  
        plaintext += new_char  
    return plaintext  
  
count_1 = 0  
count_2 = 0  
for c2 in alphabet:  
    for c3 in alphabet:  
        for c4 in alphabet:  
	        count_1 += 1
            key = "w" + c2 + c3 + c4  
            val = decrypt("SSEMA DPTLZ PTBHS JQBTY ARDYW HPX", key)  
            if "the" in val:  
                print(val)  
                print(key)
                count_2 += 1
```
From there, we get 58 plaintext + key combinations.
It was easy to pick out "wolf" and "wethepeopleoftheunitedstates" from the list of remaining answers based off the theme of the constitution recently.

---
#### Problem 1.D
If you’d had less collateral information, do you think you could have recovered the plaintext? Explain why, or why not. Include a description of the relative importance/value of each of the 4 pieces of collateral information.

"The message was encrypted with a Vigenère cipher."
> Without this bit of information, it could be pretty much any encryption scheme, and so this narrows down the search space down significantly.

"The keyword has length 4."
> This likely could have been found with some statistical analysis using Friedman's Coincident Index, but even if not it would have been pretty trivial to break if we go through all available keys from length $1$ to length $N$ and finding the ones that read English. However, there is definitely the possibility that there could be mapping that allows for another answer, and so would not be perfect.

"The keyword starts with letter W."
> This could be omitted without much worry since the chance of alternate answers are low given a small key and long input text (relatively). 

"The word "the" appears at least once in the plaintext."
> This made the search of the sample space very easy, and without it would have made it significantly harder to find the solution, but I do believe it would be possible.

Overall, I believe that some of the information could have been omitted and still get the same answer, but without knowledge that it was a Vigenère cipher and the plaintext containing "the" it would have been **significantly** harder to find the solution to the problem.

---
### Problem 2
You receive the following cipher text (in standard blocks of 5 characters), which you believe has been encrypted with a Vigenère cipher:
`SMMPF YPTMO HJNFZ PNEKV FPLQP RBLEM YXXBT PABAR RYWWU SWBLQ WSQRM GZV`
You have a spy friend who tells you that they strongly suspect the plaintext starts with the phrase “hello friends”.

| Index | Cipher | Plain | Key (C - P) |
| ----- | ------ | ----- | ----------- |
| 1     | S      | h     | l           |
| 2     | M      | e     | i           |
| 3     | M      | l     | b           |
| 4     | P      | l     | e           |
| 5     | F      | o     | r           |
| 6     | Y      | f     | t           |
| 7     | P      | r     | y           |
| 8     | T      | i     | l           |
| 9     | M      | e     | i           |
| 10    | O      | n     | b           |
| 11    | H      | d     | e           |
| 12    | J      | s     | r           |

#### Problem 2.A
What was the complete plaintext? (Your answer should be given in readable English words.)
> hello friends uh oh matched plaintext gives away a lot of information

---
#### Problem 2.B
What was the keyword?
> Liberty

---
#### Problem 2.C
What do you conclude about the vulnerability of the Vigenère cipher to a “matched plaintext-ciphertext”-style cryptanalytic attack?

> If we have a snippit of the plaintext, as well as it's starting index, we only need as many letters as is in the key in order to reverse the encryption. Since our example gave us more than the key's length of letters, especially that it is the first characters of the plaintext, we could break it very quickly.

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