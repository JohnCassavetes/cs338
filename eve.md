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

Show precisely where in your process you would have failed if the integers involved were much larger: 
> During looping to find a and b (making a while loop instead of a for loop), which will be too big to generate.

Explanation of why this wouldn't work with big integers: 
> It would be too much and take a lot of computing power to generate the number, making it inefficient.

#  RSA

e_Bob = 13
n_Bob = 162991

Found the factor by using https://www.calculatorsoup.com/calculators/math/prime-factors.php
> 389 x 419

> 162991 = 389 x 419

p = 389
q = 419

lambda(n) = lcm(p-1, q-1)
lambda(n) = lcm(389-1, 419-1)
lambda(n) = lcm(388, 418)
lambda(n) = 81092 #from https://www.calculatorsoup.com/calculators/math/lcm.php?input=388+418&data=none&action=solve

gcd(e_Bob, lambda(n)) = 1 
gcd(13, 81092) = 1 #TRUE!

e_Bob * d % lambda(n) = 1
13 * d % 81092 = 1

```bash python
for d in range(1,10000000):
    brute = (13 * d % 81092)
    print("13 * {} % 81092 = {}".format(d, brute))
    if brute == 1:
        break
```
13 * 43665 % 81092 = 1
d = 43665
d_Bob = 43665

(e_Bob, n_Bob) = (13, 162991) #Public key
(d_Bob, n_Bob) = (43665, 162991) #Secret key


```bash python
words = [17645, 100861, 96754, 160977, 120780, 90338, 130962, 74096,128123, 25052, 119569, 39404, 6697, 82550, 126667, 151824, 80067, 75272, 72641, 43884, 5579, 29857, 33449, 46274, 59283, 109287, 22623, 84902, 6161, 109039, 75094, 56614,13649, 120780, 133707, 66992, 128221]

decrypted_int = []
decrypted_str = []

for y in words:
    decrypted_int.append(y**43665 % 162991)

for thesecret in decrypted_int:
    decrypted_str.append(chr(thesecret))

print(decrypted_int)
print(decrypted_str)

thesecretmessage = "".join(decrypted_str)
print(thesecretmessage)


```

```
decrypted_int
[17509, 24946, 8258, 28514, 11296, 25448, 25955, 27424, 29800, 26995, 8303, 30068, 11808, 26740, 29808, 29498, 12079, 30583, 30510, 29557, 29302, 25961, 27756, 24942, 25445, 30561, 29795, 26670, 26991, 12064, 21349, 25888, 31073, 11296, 16748, 26979, 25902]
```
decrypted_str
```
['䑥', '慲', '⁂', '潢', 'Ⱐ', '捨', '散', '欠', '瑨', '楳', '\u206f', '畴', '⸠', '桴', '瑰', '猺', '⼯', '睷', '眮', '獵', '牶', '敩', '汬', '慮', '捥', '睡', '瑣', '栮', '楯', '⼠', '卥', '攠', '祡', 'Ⱐ', '䅬', '楣', '攮']
```
thesecretmessage: 䑥慲⁂潢Ⱐ捨散欠瑨楳⁯畴⸠桴瑰猺⼯睷眮獵牶敩汬慮捥睡瑣栮楯⼠卥攠祡Ⱐ䅬楣

after deleted the mess:
䑥慲潢捨散欠瑨楳⁯畴⸠桴瑰猺⼯睷眮獵牶敩汬慮捥睡瑣栮楯⼠卥攠祡䅬楣

translation:
呥慲榲屋 scatter owed 瑨楳⁯重⸠桴rose猺⼯睷眮hunting牶敩汬 consider捥sleep 栠楥⼠捥攠祡䅬楣