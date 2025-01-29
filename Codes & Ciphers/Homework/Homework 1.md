**Name:** Stanley Goodwin
**Date:** 1/21/2025

---
### Problem 1
Caesar wants to arrange a secret meeting with Marc Anthony, either at the Tiber (the river) or at the Coliseum (the arena). He uses a general shift cipher and sends the ciphertext `EVIRE`. However, Marc Anthony doesn’t know the key, so he tries all possibilities. Where will he meet Caesar? (Hint: this is bit of a trick question.) Write a careful description of what you did and how you arrived at your answer. How confident are you that Marc Anthony will go to the correct meeting place?

> I can conclude, since the ciphertext and plaintext are of the same length, that Caesar wants to meet at `Tiber`, the river, since Tiber is a 5-letter word, and the Coliseum is not.
> I'm an idiot. Both are 5 letter words...

### Problem 2
A problem with the general substitution cipher method of encryption is the difficulty of remembering such a long key. A technique for simplifying this is to use a keyword to generate the permutation/key. For example, suppose your keyword is `TIGER`. From this we generate a permutation/key by starting with the keyword and then filling in the rest of the letters which do not appear in the keyword (in alphabetical order).
```
plain : a b c d e f g h i j k l m n o p q r s t u v w x y z
cipher: T I G E R A B C D F H J K L M N O P Q S U V W X Y Z
```
Note: If your keyword has repeated letters, you just drop the multiple occurrences of the same letter. The keyword `CRYPTOGRAPHY` would generate the following key:
```
plain : a b c d e f g h i j k l m n o p q r s t u v w x y z
cipher: C R Y P T O G A H B D E F I J K L M N Q S U V W X Z
```
Suppose you are given the following set of matched plaintext and ciphertext, along with the information that a general substitution cipher was used, following the above keyword method.
```
plain text:  how many roads must a man walk down before you call him a man
cipher text: BMW JPKY RMPCS JUST P JPK WPHG CMWK EILMRI YMU NPHH BDJ P JPK
```
#### Problem 2.A
What was the keyword? Write up a careful description of how you determined this.

Starting with the text 1-to-1 correspondences, we get that:
```
plain : a b c d e f g h i j k l m n o p q r s t u v w x y z
cipher: P _ N C I _ _ B D _ G H J K M _ _ R S T U _ W _ Y _
```
An observation we can make is after the key has been made, if there is as many gaps as there are letters between two letters from the end, it must be those letters there, and so:
```
plain : a b c d e f g h i j k l m n o p q r s t u v w x y z
cipher: P _ N C I _ _ B D _ G H J K M O Q R S T U V W X Y Z
```
Finally, we can notice that letters `A, E, F, L` are remaining.
With a bit of deduction, we can figure out that the final substitution is:
```
plain : a b c d e f g h i j k l m n o p q r s t u v w x y z
cipher: P E N C I L A B D F G H J K M O Q R S T U V W X Y Z
```
This maintains that they are in alphabetical ordering after the key, as well as spelling a word.
Therefore, the key is `PENCIL`.

#### Problem 2.B
Using the key you recovered in 2.A, encrypt the following plain text message: `jumping jack flash`. What is the cipher text?

Using the following table:
```
plain : a b c d e f g h i j k l m n o p q r s t u v w x y z
cipher: P E N C I L A B D F G H J K M O Q R S T U V W X Y Z
```
We can find that:
```
plain : jumping jack flash
cipher: FUJODKA FPNG LHPSB
```

### Problem 3
You receive the following cipher text which you believe was encrypted with a general substitution cipher.
```
BXOPI CQOIL RZZIA FYOPQ OGIQA UICBV IWBXQ PFRLI BXQVB CCQTI OPQOC FFHIW QSAFL LOPIA BVIAQ XWOPI NCQBX OFOPI ZFRXO QBXLB XOPIE IWFYO PIABV IAOPI AIUIA INIEE CILQX WEFRC WIALW AGQXW UPBOI BXOPI LRXQX WOPIU QOIAU QLSCI QAQXW LUBYO CGZFV BXTQX WECRI BXOPI SPQXX ICLOA FFNLU IXOEG OPIPF RLIQX WWFUX OPIAF QWQXW OPIWR LOOPI GAQBL IWNFU WIAIW OPICI QVILF YOPIO AIIL
```
Perform cryptanalysis and find the plain text message. (Your answer should be given in understandable English sentences.) Provide as much of the permutation/key as you are able to recover from this message. Describe the pieces that are missing, and why. Write up a careful description of how you broke this, what techniques you used (including anything that didn’t work), and how you arrived at your answer.

> After a considerable amount of programming, I was able to get these following bits of data relating to the frequencies of mono, di, and tri, graphs, as well as double letters.
```
MONOGRAPHS
etaoinshrdlcumwfgypbvkjxqz
IOQXPWAFLBCUREVGNYZSTHDJKM

DIGRAPHS
th he in er an re nd at on nt ha es st en ed to it ou ea hi is or ti as te et ng
OP PI IA BX QX XO XW IW IL IC QO AF YO IQ VI FR WO AI CQ OI FY PQ UI BV XQ RL LI
of al de se le sa si ar ve ra ld ur
IB LO AQ QB CI LR QA AU PF QV VB IO

TRIGRAPHS
the and tha ent ion tio for nde has nce edt tis oft sth
OPI QXW BXO XOP PIA WOP FYO YOP BVI IBX XWO IAI PIC QOI

DOUBLES (this didn't turn out to be very useful in this case)
lltteessoorrddffppnnhhmmccggwwyyaabbiijjkkqquuvvxxzz
FFZZCCLLEEXXWWOOII
```
> Assuming these are all correct, we can write a table that correlates certain letters to certain other letters, and in parathesis I will have the number of occurrences.

> One of the first things that's very much apparent is the word "the" becomes very apparent, with the mono, bi, and tri, graphs showing that "O=t, P=h, I=e."
> This has been reflected in the next table (removing other characters that map to those.)

| Plaintext Letter | Cipher Letter                                     |
| ---------------- | ------------------------------------------------- |
| a                | Q(4) V(2) O(2) B(1) L(1) R(1) A(1) I(1)           |
| b                | S(1)                                              |
| c                | U(1) B(1)                                         |
| d                | W(3) A(1) B(1) I(1) D(1) O(1)                     |
| e                | I(5) B(2) O(1) X(3) P(1) A(1) C(1) Q(2) R(1) F(1) |
| f                | G(1) B(1) F(1) I(1)                               |
| g                | N(1) I(1)                                         |
| h                | P(3) F(1) Q(1) O(1) X(1) B(1) I(1)                |
| i                | P(2) I(3) W(1) F(1) A(2) O(1)                     |
| j                | D(1)                                              |
| k                | H(1)                                              |
| l                | C(2) O(1) V(1)                                    |
| m                | E(1)                                              |
| n                | W(1) A(2) X(3) L(2) I(2) Q(1) O(1) Y(1)           |
| o                | X(1) I(3) L(1) R(1) A(1) P(2) O(1) Y(1)           |
| p                | Z(1)                                              |
| q                | K(1)                                              |
| r                | L(1) X(2) Q(2) U(1) O(2)                          |
| s                | A(1) F(1) Y(2) V(1) Q(3) L I(2)                   |
| t                | O(6) W(2) C(2) U(1) X(1) L(1) B(1) P(1) I(1)      |
| u                | I(2) R(1)                                         |
| v                | T(1) P(1)                                         |
| w                | V(1)                                              |
| x                | J(1)                                              |
| y                | Y(1)                                              |
| z                | M(1)                                              |
**Table 1:** Raw Data from Monographs, Digraphs, and Trigraphs.

| Plaintext Letter | Cipher Letter                 |
| ---------------- | ----------------------------- |
| a                | Q(4) V(2) B(1) L(1) R(1) A(1) |
| b                | S(1)                          |
| c                | U(1) B(1)                     |
| d                | W(3) A(1) B(1) D(1)           |
| **e**            | **I**                         |
| f                | G(1) B(1) F(1)                |
| g                | N(1)                          |
| **h**            | **P**                         |
| i                | W(1) F(1) A(2)                |
| j                | D(1)                          |
| k                | H(1)                          |
| l                | C(2) V(1)                     |
| m                | E(1)                          |
| n                | X(3) A(2) W(1) L(2 Q(1) Y(1)  |
| o                | X(1) L(1) R(1) A(1) Y(1)      |
| p                | Z(1)                          |
| q                | K(1)                          |
| r                | L(1) X(2) Q(2) U(1)           |
| s                | A(1) F(1) Y(2) V(1) Q(3) L    |
| **t**            | **O**                         |
| u                | R(1)                          |
| v                | T(1)                          |
| w                | V(1)                          |
| x                | J(1)                          |
| y                | Y(1)                          |
| z                | M(1)                          |
**Table 2:** Observation that "OPI" -> "the" from all 3 of the types.
```
BXthe CQteL RZZeA FYthQ tGeQA UeCBV eWBXQ hFRLe BXQVB CCQTe thQtC FFHeW QSAFL LtheA BVeAQ XWthe NCQBX tFthe ZFRXt QBXLB XtheE eWFYt heABV eAthe AeUeA eNeEE CeLQX WEFRC WeALW AGQXW UhBte BXthe LRXQX WtheU QteAU QLSCe QAQXW LUBYt CGZFV BXTQX WECRe BXthe ShQXX eCLtA FFNLU eXtEG thehF RLeQX WWFUX theAF QWQXW theWR Ltthe GAQBL eWNFU WeAeW theCe QVeLF Ythet AeeL
```
> The next that stand out is that `Q->a`, `X->n`, and `W->d`.
> This is my guess since it relates to another common word `and`.

| Plaintext Letter | Cipher Letter            |
| ---------------- | ------------------------ |
| **a**            | **Q**                    |
| b                | S(1)                     |
| c                | U(1) B(1)                |
| **d**            | **W**                    |
| **e**            | **I**                    |
| f                | G(1) B(1) F(1)           |
| g                | N(1)                     |
| **h**            | **P**                    |
| i                | F(1) A(2)                |
| j                | D(1)                     |
| k                | H(1)                     |
| l                | C(2) V(1)                |
| m                | E(1)                     |
| n                | **X**                    |
| o                | L(1) R(1) A(1) Y(1)      |
| p                | Z(1)                     |
| q                | K(1)                     |
| r                | L(1) U(1)                |
| s                | A(1) F(1) Y(2) V(1) L(1) |
| **t**            | **O**                    |
| u                | R(1)                     |
| v                | T(1)                     |
| w                | V(1)                     |
| x                | J(1)                     |
| y                | Y(1)                     |
| z                | M(1)                     |
**Table 3:** Observation that "QWX" -> "adn" from observation
```
BXtheCQteLRZZeAFYthQtGeQAUeCBVeWBXQhFRLeBXQVBCCQTethQtCFFHeWQSAFLLtheABVeAQXWtheNCQBXtFtheZFRXtQBXLBXtheEeWFYtheABVeAtheAeUeAeNeEECeLQXWEFRCWeALWAGQXWUhBteBXtheLRXQXWtheUQteAUQLSCeQAQXWLUBYtCGZFVBXTQXWECReBXtheShQXXeCLtAFFNLUeXtEGthehFRLeQXWWFUXtheAFQWQXWtheWRLttheGAQBLeWNFUWeAeWtheCeQVeLFYthetAeeL
```
> At this point, the table becomes not very useful since there's a small amount of letters.

> Trying to read it as English, I can see some certain things that help with getting a full answer.
```
Bn the CateLRZZeAFYthatGeaAUeCBVedBnahFRLeBnaVBCCaTethatCFFHedaSAFLL the ABVeA and the NCaBntF the ZFRntaBnLBn the EedFY the ABVeA the AeUeAeNeEECeL and EFRCdeALdAG and UhBteBn the LRn and the UateAUaLSCeaA and LUBYtCGZFVBnT and ECReBn the ShanneCLtAFFNLUentEG the hFRLe and dFUn the AFad and the dRLt the GAaBLedNFUdeAed the CeaVeLFY the tAeeL
```
> I purposely separated the "and" and "the" words, even though they may be part of a larger word.

Assuming `B -> i`:
```
in the CateLRZZeAFYthatGeaAUeCiVedinahFRLeinaViCCaTethatCFFHedaSAFLL the AiVeA and the NCaintF the ZFRntainLin the EedFY the AiVeA the AeUeAeNeEECeL and EFRCdeALdAG and Uhitein the LRn and the UateAUaLSCeaA and LUiYtCGZFVinT and ECRein the ShanneCLtAFFNLUentEG the hFRLe and dFUn the AFad and the dRLt the GAaiLedNFUdeAed the CeaVeLFY the tAeeL
```
> The word "river" came from knowing "i" and "e", and looking at words that start and end with the same letter, where it makes sense in context.
Assuming `A -> r` and `V -> v`:
```
in the CateLRZZerFYthatGearUeCivedinahFRLeinaviCCaTethatCFFHedaSrFLL the river and the NCaintF the ZFRntainLin the EedFY the river the reUereNeEECeL and EFRCderLdrG and Uhitein the LRn and the UaterUaLSCear and LUiYtCGZFvinT and ECRein the ShanneCLtrFFNLUentEG the hFRLe and dFUn the rFad and the dRLt the GraiLedNFUdered the CeaveLFY the treeL
```
> At the end, I can guess that it's supposed to be `trees`, and so we can substitute.
Assuming `L -> s`:
```
in the CatesRZZerFYthatGearUeCivedinahFRseinaviCCaTethatCFFHedaSrFss the river and the NCaintF the ZFRntainsin the EedFY the river the reUereNeEECes and EFRCdersdrG and Uhitein the sRn and the UaterUasSCear and sUiYtCGZFvinT and ECRein the ShanneCstrFFNsUentEG the hFRse and dFUn the rFad and the dRst the GraisedNFUdered the CeavesFY the trees
```
> The word `ZFRntainsin` is almost certainly `mountains in`, and so:
Assuming `Z -> m`, `F -> o`, and `R -> u`:
```
in the Cate summer oY that GearUeCivedinahouseinaviCCaTethatCooHedaSross the river and the NCainto the mountains in the EedoY the river the reUereNeEECes and EouCdersdrG and Uhite in the sun and the Uater Uas SCear and sUiYtCGmovinT and ECuein the ShanneCstrooNsUentEG the house and doUn the road and the dust the GraisedNoUdered the CeavesoY the trees
```
> The words `Uater Uas` is almost certainly `water was`, as well as `oY` being `of`
Assuming `U -> w` and `Y -> f`:
```
in the Cate summer of that Gear we Cived in a house in aviCCaTe that CooHedaSross the river and the NCainto the mountains in the Eedof the river the rewereNeEECes and EouCdersdrG and white in the sun and the water was SCear and swiftCG movinT and ECuein the ShanneCstrooNswentEG the house and down the road and the dust the GraisedNowdered the Ceavesof the trees
```
> The words `movinT -> moving`, `Cived -> lived`, `SCear -> clear`, and `swiftCG -> swiftly`.
Assuming `T -> g`, `C -> l`, `S -> c`, and `G -> y`:
```
in the late summer of that year we lived in a house in a village that looHed across the river and the Nlain to the mountains in the Eed of the river the rewereNeEEles and Eoulders dry and white in the sun and the water was clear and swiftly moving and Eluein the channelstrooNswentEy the house and down the road and the dust they raisedNowdered the leaves of the trees
```
> The words `looHed -> looked`, `Eed -> bed`.
Assuming `H -> k`, and `E -> b`:
```
in the late summer of that year we lived in a house in a village that looked across the river and the Nlain to the mountains in the bed of the river the rewereNebbles and boulders dry and white in the sun and the water was clear and swiftly moving and bluein the channelstrooNs went by the house and down the road and the dust they raised Nowdered the leaves of the trees
```
> From here, I can make my final guess.
#### Plaintext
```
in the late summer of that year we lived in a house in a village that looked across the river and the plain to the mountains in the bed of the river there were pebbles and boulders dry and white in the sun and the water was clear and swiftly moving and blue in the channels troops went by the house and down the road and the dust they raised powdered the leaves of the trees
```
#### Cipher Key
```
plaintext : abcdefghijklmnopqrstuvwxyz
ciphertext: QESWIYTPB_HCZXFN_ALORVU_G_
```
> There are some letters that don't exist, and so I've left them as underscores.
> They don't seem to make word in the cipher text, so there's nothing left to be done.