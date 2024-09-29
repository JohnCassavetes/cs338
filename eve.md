Jeremy Gautama

#  Diffie-Hellman

### Alice
1. A = g^a % p
2. A = 7^a % 97
3. 53 = 7^a % 97

    Finding the a using this code:
    ```bash python
    for a in range(1,100):
        brute = (7**a) % 97
        print("(7**{}) % 97: {}".format(a, brute))
        if brute == 53:
            break
    ```
    > (7**22) % 97: 53\
    > a = 22

### Bob
1. B = g^b % p
2. B = 7^b % 97
3. 82 = 7^b % 97

    Finding the b using this code:
    ```bash python
    for b in range(1,100):
        brute = (7**b) % 97
        print("(7**{}) % 97: {}".format(b, brute))
        if brute == 82:
            break
    ```
    > (7**41) % 97: 82\
    > b = 41

### Facts: A = 53, B = 82, g = 7, p = 97, a = 22, b = 41

1. K = A^b % p
2. K = 53^41 % 97
3. **K = 65**
---
1. K = B^a % p
2. K = 82^22 % 97
3. **K = 65**

### The Shared Secret is 65!

### Q&A
Show precisely where in your process you would have failed if the integers involved were much larger: 
> During looping to find a and b (making a while loop instead of a for loop), which will be too big to generate.

Explanation of why this wouldn't work with big integers: 
> It would be too much and take a lot of computing power to generate the number, making it inefficient.

#  RSA

Basically following the exact steps as the lab...

### Trying to find `d_Bob`
Facts we know now:
```
e_Bob = 13
n_Bob = 162991
```

The factor of 162991 is 389 x 419.
Found the factor by using [calculatorsoup.](https://www.calculatorsoup.com/calculators/math/prime-factors.php)

```
p = 389
q = 419
```
```
lambda(n) = lcm(p-1, q-1)
lambda(n) = lcm(389-1, 419-1)
lambda(n) = lcm(388, 418)
lambda(n) = 81092
```
*Found the lowest common denominator by using [calculatorsoup.](https://www.calculatorsoup.com/calculators/math/lcm.php?input=388+418&data=none&action=solve)

Checking to see if the Greatest Common Denominator of 13 and 81092 is 1.
```
gcd(e_Bob, lambda(n)) = 1
gcd(13, 81092) = 1
```
It is!

Now we're trying to find `d_Bob`.
```
e_Bob * d_Bob % lambda(n) = 1
13 * d_Bob % 81092 = 1
```
Finding d_Bob with this code:
```bash python
for d_Bob in range(1,10000000):
    brute = (13 * d_Bob % 81092)
    print("13 * {} % 81092 = {}".format(d_Bob, brute))
    if brute == 1:
        break
```
```
After the brute, founded that 
d_Bob = 43665.

And 13 * 43665 % 81092 = 1
```
>d_Bob is 43665!

### Things we know now

```
(e_Bob, n_Bob) = (13, 162991) #Public key
(d_Bob, n_Bob) = (43665, 162991) #Secret key
```

### Decrypting the message
```bash python
encrypted_words = [17645, 100861, 96754, 160977, 120780, 90338, 130962, 74096,128123, 25052, 119569, 39404, 6697, 82550, 126667, 151824, 80067, 75272, 72641, 43884, 5579, 29857, 33449, 46274, 59283, 109287, 22623, 84902, 6161, 109039, 75094, 56614,13649, 120780, 133707, 66992, 128221]

decrypted_int = []
decrypted_str = []

for y in encrypted_words:
    decrypted_int.append(y**43665 % 162991)

for thesecret in decrypted_int:
    decrypted_str.append(chr(thesecret))

print(decrypted_int)
print(decrypted_str)
print("".join(decrypted_str))
```

```
decrypted_int output:
[17509, 24946, 8258, 28514, 11296, 25448, 25955, 27424, 29800, 26995, 8303, 30068, 11808, 26740, 29808, 29498, 12079, 30583, 30510, 29557, 29302, 25961, 27756, 24942, 25445, 30561, 29795, 26670, 26991, 12064, 21349, 25888, 31073, 11296, 16748, 26979, 25902]
```

```
decrypted_str output:
['䑥', '慲', '⁂', '潢', 'Ⱐ', '捨', '散', '欠', '瑨', '楳', '\u206f', '畴', '⸠', '桴', '瑰', '猺', '⼯', '睷', '眮', '獵', '牶', '敩', '汬', '慮', '捥', '睡', '瑣', '栮', '楯', '⼠', '卥', '攠', '祡', 'Ⱐ', '䅬', '楣', '攮']

decrypted_str as a string:
䑥慲⁂潢Ⱐ捨散欠瑨楳⁯畴⸠桴瑰猺⼯睷眮獵牶敩汬慮捥睡瑣栮楯⼠卥攠祡Ⱐ䅬楣
```

### The decrypted message is 䑥慲⁂潢Ⱐ捨散欠瑨楳⁯畴⸠桴瑰猺⼯睷眮獵牶敩汬慮捥睡瑣栮楯⼠卥攠祡Ⱐ䅬楣


### Q&A
Explanation of why this wouldn't work with big integers?
> Because it will be hard to find the `d_Bob`, by not only having to brute more and more, but also finding the factor of `n_Bob`.

Explanation of why the encoding is insecure independent of RSA?
> Because if the message is small, the encryption is small as well. So the man-in-the-middle could easily guess the message.