**Name:** Stanley Goodwin
**Date:** 2/17/2025

---
## Machine Ciphers
### Enigma Machine
Invented by Arthur Scherbius, being an electrical version of Alberti's Cipher Disc.
#### How Does It Work?
There is a set of 3 scrambler discs that map 1-to-1 letters, in series, and then the signal is reflected back the way it came and then displayed.
#### Number of Combinations
For the 3 rotors, we find that (initial orientations):
$$26\cdot26\cdot26=17576\text{ Orientations}$$
The number of permutations of 3 rotors:
$$3!=6\text{ Permutations}$$
In total, we can product the two to find the final amount of settings + key:
$$6\cdot26\cdot26\cdot26=105456\text{ Configurations}$$
They also have plugboards, which have 6 cables that connect pairs of letters.
$$\left(\begin{array}{c}26\\12\end{array}\right)\cdot11!!=100391791500\text{ Plugboard Combinations}$$
So, the real total of combinations is:
$$10,586,916,764,424,000\text{ Total Configurations}$$
#### Breaking Enigma
Some ways that were used to break this encoding
 - Obtaining copies of the user manual (replication of machine).
 - Structure of plaintext repeating plaintext strings.
 - Plugboard copy eliminated certain key swaps.
 - A *Bombe* was build to brute-force key settings.

---

## Post WWII
Machines such as the M-209, SIGABA (ECM MKII / M-134), were created by the United States for encrypting and decrypting messages.
Secure voice radio was created that could transmit voice without losing information, although the quality was not great and the machines were large and heavy.
Beyond that, encryption started being implemented digitally, and is commonplace these days.

Key distribution was the newest problem, since you required a key to decrypt information.



