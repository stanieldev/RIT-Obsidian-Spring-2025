### Problem 1
Caesar wants to arrange a secret meeting with Marc Anthony, either at the Tiber (the river) or at the Coliseum (the arena). He uses a general shift cipher and sends the ciphertext `EVIRE`. However, Marc Anthony doesn’t know the key, so he tries all possibilities. Where will he meet Caesar? (Hint: this is bit of a trick question.) Write a careful description of what you did and how you arrived at your answer. How confident are you that Marc Anthony will go to the correct meeting place?

> I can conclude, since the ciphertext and plaintext are of the same length, that Caesar wants to meet at `Tiber`, the river, since Tiber is a 5-letter word, and the Coliseum is not.

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
BXOPI CQOIL RZZIA FYOPQ OGIQA UICBV IWBXQ PFRLI BXQVB CCQTI OPQOC FFHIW QSAFL LOPIA
BVIAQ XWOPI NCQBX OFOPI ZFRXO QBXLB XOPIE IWFYO PIABV IAOPI AIUIA INIEE CILQX WEFRC
WIALW AGQXW UPBOI BXOPI LRXQX WOPIU QOIAU QLSCI QAQXW LUBYO CGZFV BXTQX WECRI BXOPI
SPQXX ICLOA FFNLU IXOEG OPIPF RLIQX WWFUX OPIAF QWQXW OPIWR LOOPI GAQBL IWNFU WIAIW
OPICI QVILF YOPIO AIIL
```
#### Problem 3.A
Perform cryptanalysis and find the plain text message. (Your answer should be given in understandable English sentences.)
#### Problem 3.B
Provide as much of the permutation/key as you are able to recover from this message. Describe the pieces that are missing, and why.
#### Problem 3.C
Write up a careful description of how you broke this, what techniques you used (including anything that didn’t work), and how you arrived at your answer.