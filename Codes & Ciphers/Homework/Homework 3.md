**Name:** Stanley Goodwin
**Date:** 2/21/2025

*Forward:* I work alone since I don't know anyone else in the class to work on these with me.
However, I don't mind too much since I quite enjoy doing these myself.

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

---
#### Problem 2.A
What was the complete plaintext? (Your answer should be given in readable English words.)
> hello friends uh oh matched plaintext gives away a lot of information

I wrote a program to take the ciphertext and key to give back the plaintext.
From there, I added spaces as needed for the sentence to make sense.

---
#### Problem 2.B
What was the keyword?
> liberty

I got this from the column of the decoded letter in the table using a calculator that would subtract the corresponding values and then applied modulus 26.

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

| Ciphertext | Starting Indices | $\Delta x$ | Factors                           |
| ---------- | ---------------- | ---------- | --------------------------------- |
| MCHLI      | 40, 92           | 52         | 2,4,13,26,52                      |
| CJXWS      | 206, 234         | 28         | 2,4,  7,14,28                     |
| RVHL       | 4, 180           | 176        | 2,4,  8,11,16,22,44,88,176        |
| DIRH       | 29, 185          | 156        | 2,3,  4,  6,12,13,26,39,52,78,156 |
| MCHL       | 40, 92           | 52         | 2,4,13,26,52                      |
| CHLI       | 41, 93           | 52         | 2,4,13,26,52                      |
| WMCU       | 115, 143         | 28         | 2,4,  7,14,28                     |
| CJXW       | 206, 234         | 28         | 2,4,  7,14,28                     |
| JXWS       | 207, 235         | 28         | 2,4,  7,14,28                     |
**Table 1:** Repeated Strings of 4 Characters

---
#### Problem 3.A
Find the length of the keyword that was used. Explain how you arrived at this answer and how confident you are that it is correct.

**Log of work in 2/8/2025**
> **4.47pm:** I can see that a common word length is 2 and 4, so I'll start with 4. Something tells me that it won't be 2, only because I feel like that would be too easy to crack.

> **5:05pm:** Whatever the letter is for the 1st character is it is likely the same for the 4th character.
> I will guess that it will take the form "XYZX" (reduce to 3 variables).
> I used frequency analysis and they matched up a little *too* perfectly.
> I can safely say that it's very unlikely that the key is of length 2.

> **5:10pm:** I don't know if the key must be a word, so I'll assume it isn't until shown otherwise.
> I'll know when I see the plaintext as legible English.

> **5:13pm:** I ran through the key length = 2 just to make sure I wasn't missing a quicker solution, but when I did, I used an online software to detect if there are words in the plaintext. While there were a few that gave some words, the rest of it was garbage, and so I can assume that the key is not of length 2. I will try 4 now that I'm more confident.

> **5:21pm:** Made a shot in the dark. I did a 4x for loop, followed by a 3x for loop using the 1st and 4th characters of the key are likely the same. I used a list of most common words in English and used "The" to see if I could find any.
> As you might expect, there were a lot of "the" in garbage sentences, but I then made it only print those with >2 "the", then >3 "the", and so on. When I used >3, I got the following list of outputs:

```python
SEARCH = "the"  
for c1 in alphabet:  
    for c2 in alphabet:  
        for c3 in alphabet:  
            key = c1 + c2 + c3 + c1  
            val = decrypt(ciphertext, key)  
            if val.count(SEARCH) > 3:  
                print(val)  
                print(key)
```

| Key  | plaintext output                                      |
| ---- | ----------------------------------------------------- |
| ecoe | dhrintthejholrofaqullqarknndsbundyessqayiathenutuz... |
| eooe | dvrinhthexholfofaeullearkbndspundmesseayiothebutu...  |
| epoe | duringthewholeofadulldarkandsoundlessdayintheautu...  |
> Bingo! There's the answer. I wasn't expecting to get it that quickly. I thought I would have had to try a few more combinations of quantities and frequent words before finding the answer.

---
#### Problem 3.B
Determine the keyword that was used. Fully show or describe the work you did to arrive at this answer, and how confident you are that it is correct.
> epoe

> I'm fairly confident that this is correct since I was able to use the first 10 or so words of the plaintext to look up what the source of it was. Turns out it was Edgar Allen Poe, as found here:
> https://www.goodreads.com/quotes/504815-during-the-whole-of-a-dull-dark-and-soundless-day

> I also now understand why "epoe" was chosen, standing for Edgar Poe (E. Poe), which makes a lot more sense than before I looked up the source material.

---
#### Problem 3.C
Decrypt the cipher text and recover the plain text, writing it in readable English sentences. (Make your best guess at punctuation, capitalization, and sentence structure.)

**Raw output text**
> "during the whole of a dull dark and soundless day in the autumn of the year when the clouds hung oppressively low in the heavens i had been passing alone on horseback through a singularly dreary tract of country and at length found myself as the shades of the evening drew on within view of the melancholy house of usher"

**With proper formatting**
> "During the whole of a dull, dark, and soundless day in the autumn of the year, when the clouds hung oppressively low in the heavens, I had been passing alone, on horseback, through a singularly dreary tract of country; and at length found myself, as the shades of the evening drew on, within view of the melancholy House of Usher."
>  - *Edgar Allen Poe, The Fall of the House of Usher and Other Tales*

---
#### Problem 3.D
Compute the observed index of coincidence for the cipher text, and use it to “predict” the length of the keyword. How accurate is this prediction? Describe some of the limitations of using the index of coincidence.

I wrote some code to do the math for me:
```python
I_e = 0.0656  
I_r = 0.0385  

amounts = [ciphertext.count(c) for c in ALPHABET]  
contribution = [a*(a-1) for a in amounts]  
I_c = sum(contribution) / (len(ciphertext) * (len(ciphertext) - 1))  
k_approx = (I_e - I_r) / (I_c - I_r)

print(f"{I_c=}")  
print(f"{k_approx=}")
```
When I printed, I got the values:
$I_c=0.05104627173592691$
$k\approx2.1600042283794743$

> After solving the cipher, I can see that the estimation was too low.
> Seeing that the key had 2 "e" in it, I can see why it was lower than 4, being that it's effectively only 3 different letters for the key.
> This is a known problem with this method that it only gives you a lower bound pretty reasonably instead of the exact value of the length of the key.
> The index of coincidence is a statistical property of the data, and so can vary with the input to an extend where it is noticeable, especially in cryptography.