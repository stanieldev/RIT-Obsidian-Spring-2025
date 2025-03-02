**Name:** Stanley Goodwin
**Date:** 2/24/2025

---
### Problem 1
The following ciphertext was encrypted by an affine cipher:
```
A GCRB BK ICC BHC JKQBKP KV DHAFKIKDHS
```
Word boundaries have been preserved in the encryption process and you receive the collateral information that the word “the” is in the plaintext. Use the matched plaintext-ciphertext style attack we described in class to recover the key and the underlying plaintext.

---
#### Problem 1.A
What was the key?
> $a=19$, $b=4$
---
#### Problem 1.B
What is the decryption function?
> $\begin{align}D(C)&=19^{-1}(C-4)\mod26\\&=11(C-4)\mod26\\&=11C-44\mod26\\\Aboxed{D(C)&=11C+8\mod26}\end{align}$
---
#### Problem 1.C
What was the plaintext?
> i went to see the doctor of philosophy
---
#### Problem 1.D
Document your work fully, describing the techniques you used (and anything that didn’t work).

> I wrote a program to loop over all combinations of $a$ and $b$ that were possible, and only printed those of which contained the word "the" in them.
```python
def affine_brute_force(ciphertext: str, *, known_string: str|None=None) -> None:  
    ALPHA: list[int] = [1, 3, 5, 7, 9, 11, 15, 17, 19, 21, 23, 25]  
    BETA:  list[int] = list(range(26))    
    for a in ALPHA:  
        for b in BETA:  
            plaintext = affine_decrypt(ciphertext, a, b)  
            if known_string is not None and known_string not in plaintext:  
                continue  
            print(f"{a=}, {b=}, {plaintext=}")
  
if __name__ == "__main__":  
    CIPHERTEXT = "A GCRB BK ICC BHC JKQBKP KV DHAFKIKDHS".replace(" ", "")  
    affine_brute_force(CIPHERTEXT, known_string="the")
```

> It is definitely possible to do this without brute force since we were given the spacing between the words. There's only 2 keys that could exist, `ICC -> the` or `BHC -> the`, and it's obvious to show that `ICC` cannot be the key since there's a repeated `C`, and so `BHC -> the`.
$$\begin{align}
\text{"t"}&=a^{-1}\left(\text{"B"}-b\right)&\mod 26\\
19&=a^{-1}\left(1-b\right)&\mod 26\\
\text{"h"}&=a^{-1}\left(\text{"H"}-b\right)&\mod 26\\
7&=a^{-1}\left(7-b\right)&\mod 26\\
\text{"e"}&=a^{-1}\left(\text{"C"}-b\right)&\mod 26\\
4&=a^{-1}\left(2-b\right)&\mod 26\\
\end{align}$$
> We can the write it as a system of equations:
$$\begin{align}
19a+b&=1&\mod 26\\
7a+b&=7&\mod 26\\
4a+b&=2&\mod 26\\
\end{align}$$
> From there we can see a solution $a=19$ and $b=4$.

---
### Problem 2
Alice is sending encrypted messages to Bob using a Hill cipher with block size 2. Eve acquires access to Alice’s encryption device and is able to quickly submit the plaintext "warble" through the device and determines that the corresponding ciphertext is "CUSTDK".
#### Problem 2.A
Determine the $2\times2$ key matrix.
> $A=\begin{bmatrix}19&7\\8&13\end{bmatrix}$
> Using the word "warble" and "CUSTDK" gave me enough information to uniquely define the matrix, so I didn't need to test multiple solutions on 2.B to verify which was which.

---
#### Problem 2.B
Eve acquires the ciphertext:
```
HYPNN IWVHE IOEOG OBDBT
```
which Alice sent to Bob using this same cipher. Use the key you recovered in part (a) to decrypt this message. Give your answer in readable English words (or sentences, if appropriate).
> dear bob this is a secret

---
#### Problem 2.C
Write up a careful description of how you broke this, what techniques you used (including anything that didn’t work), and how you arrived at your answer.

> I wrote a program to loop over all 2x2 matrices, skipped the ones who's determinants were factors of 13 or 2, then waited to match the input and output expected thanks to Eve.
```python
if __name__ == "__main__":  
    for a in range(26):  
        for b in range(26):  
            for c in range(26):  
                for d in range(26):  
                    # Calculate the determinant of the matrix  
                    determinant = (a * d - b * c) % 26  
                    if determinant % 2 == 0 or determinant % 13 == 0:  
                        continue  
  
                    matrix = np.array([[a, b], [c, d]])  
                    ciphertext = hill_encrypt(PLAINTEXT, matrix)  
                    if ciphertext == CIPHERTEXT.lower():  
                        print(f"{matrix=}, {ciphertext=}")  
                        break  
                else:  
                    continue  
                break
```
> From there, I had to find the inverse matrix under mod 26, and after using the inverse matrix of a 2x2 and inverse determinant, I was able to find that:
> (incorrect matrix, it's the transpose)
$$A=\begin{bmatrix}19&8\\7&13\end{bmatrix}\implies A^{-1}=\begin{bmatrix}13&2\\5&5\end{bmatrix}$$
> Using the inverse, it's quite simple to find the plain text from there. I wrote code to do the multiplications for me and the conversion back to string letters.

---
### Problem 3
You receive the ciphertext
```
KFQUN CIKQB
```
which has been encrypted with the Playfair cipher and keyword CRYPTOGRAPHY.

> I can then write the following square as (CRYPTOGAH):
$$\begin{array}{}
C&R&Y&P&T\\
O&G&A&H&B\\
D&E&F&I&K\\
L&M&N&Q&S\\
U&V&W&X&Z\\
\end{array}$$
> Now I can use this to work for part A and B.

---
#### Problem 3.A
What was the original plaintext? (Your answer should be an understandable English word/s)

| Digraph | Operation | New Digraph |
| ------- | --------- | ----------- |
| KF      | S. Row    | I/J, E      |
| QU      | Rectangle | LX          |
| NC      | Rectangle | LY          |
| IK      | S. Row    | FI          |
| QB      | Rectangle | SH          |
> Concatenating, we can see `I/J ELXLYFISH`. `X` is usually used to separate double characters, and it makes sense to use `J` here based on context.

> Therefore, the plaintext is `jellyfish`

---
#### Problem 3.B
Using the Playfair cipher and the same key from part (a), encrypt the plaintext
```
rubber soul
```
and give your answer in 5-character ciphertext blocks.

| Digraph | Operation | New Digraph |
| ------- | --------- | ----------- |
| ru      | Rectangle | CV          |
| bx      | Rectangle | HZ          |
| be      | Rectangle | GK          |
| rs      | Rectangle | TM          |
| ou      | S. Col    | DC          |
| lx      | Rectangle | QU          |
> Therefore, our ciphertext is `CVHZG KTMDC QU`.

---
### Problem 4
Here is a scheme to generate a $6\times6$ key matrix to use with an ADFGVX cipher.
 - Pick a word and a 5-digit number (the number should not have repeated digits). E.g., snowman 13209.
 - Start filling out the 6 × 6 grid by interleaving the (non-repeating) letters in the word and the digits in the number.
 - When you run out of letters in the word, fill in the rest of alphabet alphabetically.
 - When you run out of numbers, fill in the rest of the digits in numerical order, continuing to interleave as long as you can.
Here’s the grid generated by snowman 13209:
$$\begin{array}{}
s&1&n&3&o&2\\
w&0&m&9&a&4\\
b&5&c&6&d&7\\
e&8&f&g&h&i\\
j&k&l&p&q&r\\
t&u&v&x&y&z
\end{array}$$
Recall that the $6\times6$ grid is only one part of the key. The Stage 2 key is a keyword. For this, we could use the same word that generated the grid or a different word.

---
#### Problem 4.A
Using the above scheme, with Stage 1 key: garbage 25086, and with Stage 2 keyword: BLANK, encrypt the following message with the ADFGVX cipher:
```
dark side of the moon
```
> We can make the table as the following (I kept messing this up)
$$\begin{array}{c|c|}
&A&D&F&G&V&X\\
A&g&2&a&5&r&0\\
D&b&8&e&6&c&1\\
F&d&3&f&4&h&7\\
G&i&9&j&k&l&m\\
V&n&o&p&q&s&t\\
X&u&v&w&x&y&z\\
\end{array}$$
> I will make a list of for each conversion as the following:
```
d  a  r  k  s  i  d  e  o  f  t  h  e  m  o  o  n
FA AF AV GG VV GA FA DF VD FF VX FV DF GX VD VD VA
```
> Which turns into:
```
FAAFA VGGVV GAFAD FVDFF VXFVD FGXVD VDVA
```
> Turning this into a table, we can see that:

| B   | L   | A   | N   | K   |
| --- | --- | --- | --- | --- |
| F   | A   | A   | F   | A   |
| V   | G   | G   | V   | V   |
| G   | A   | F   | A   | D   |
| F   | V   | D   | F   | F   |
| V   | X   | F   | V   | D   |
| F   | G   | X   | V   | D   |
| V   | D   | V   | A   | X   |
> We can then put the key in alphabetical order, so:

| A   | B   | K   | L   | N   |
| --- | --- | --- | --- | --- |
| A   | F   | A   | A   | F   |
| G   | V   | V   | G   | V   |
| F   | G   | D   | A   | A   |
| D   | F   | F   | V   | F   |
| F   | V   | D   | X   | V   |
| X   | F   | D   | G   | V   |
| V   | V   | X   | D   | A   |
> Reading it top to bottom, then left to right, we get the final encrypted ciphertext:
```
AGFDF XVFVG FVFVA VDFDD XAGAV XGDFV AFVVA
```

---
#### Problem 4.B
Suppose you receive the following ciphertext:
```
AVDDD XDVAV DAAAX GVVFG VAVVF AFAFV
```
which was created with an ADFGVX cipher and the same keys used in part (a). What was the
plaintext?

| A   | B   | K   | L   | N   |
| --- | --- | --- | --- | --- |
| A   | D   | A   | F   | F   |
| V   | V   | A   | G   | A   |
| D   | A   | X   | V   | F   |
| D   | V   | G   | A   | A   |
| D   | D   | V   | V   | F   |
| X   | A   | V   | V   | V   |
> We can then put the key in the key order, so:

| B   | L   | A   | N   | K   |
| --- | --- | --- | --- | --- |
| D   | F   | A   | F   | A   |
| V   | G   | V   | A   | A   |
| A   | V   | D   | F   | X   |
| V   | A   | D   | A   | G   |
| D   | V   | D   | F   | V   |
| A   | V   | X   | V   | V   |
> Reading it left to right, then down, we get:
```
DFAFA VGVAA AVDFX VADAG DVDFV AVXVV
```
> I will make a list of for each conversion as the following:
```
DF AF AV GV AA AV DF XV AD AG DV DF VA VX VV
e  a  r  l  g  r  e  y  2  5  c  e  n  t  s
```
> Which turns into:
```
earl grey 25 cents
```
> Earl Gray!! I drink that!

---
### Problem 5
Suppose you receive the following ciphertext:
```
UOGRK QSXNK ACPTK ACCEN I
```
and you know the following collateral information:
 - The encryption was performed using an autokey cipher.
 - The keyword length is 5.
 - The word “the” appears at least once in the plaintext.
---
#### Problem 5.A
Recover the keyword and the plaintext. (The plaintext should be given in understandable English words.)
> Key: Unknown
> Plaintext: Unknown

---
#### Problem 5.B
Write up a careful description of how you broke this, what techniques you used (including anything that didn’t work), and how you arrived at your answer.

> I started by writing a program that brute forces all 5-character keys and single out those of which who have a "the" somewhere in them. This dropped the space from 11,881,376 answers to 6957 possible solutions. From there, I spent *way* too long looking through the answers. I didn't find it. I might upload a revision tomorrow with the answer but I don't think I'm gonna get it in time.

---
### Problem 6
Suppose a variant of the Enigma is built with two more cables in the plugboard, so that now there are 8 cables available to swap 8 pairs of letters instead of 6. How many additional key/settings does this provide?

> Remembering what we did in lecture for six plugboard connections, we get:
$$\left(\begin{array}{c}26\\2\cdot6\end{array}\right)\cdot(2\cdot6-1)!!=100391791500\text{ Plugboard Combinations}$$
> For eight, it's very similar since it follows a pretty general form:
$$\left(\begin{array}{c}26\\2\cdot8\end{array}\right)\cdot(2\cdot8-1)!!=10767019638375\text{ Plugboard Combinations}$$
> If we take the ratio of the eight plugboard to six plug board, we get:
$$\dfrac{10767019638375}{100391791500}=107.25$$
> So there are 107.25 times the number of combinations with eight plugs than six.
