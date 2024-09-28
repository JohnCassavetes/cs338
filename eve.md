Jeremy Gautama

#  Diffie-Hellman

### Alice sent Bob the number 53.
1. A = g^a % p
2. A = 7^a % 97
3. 53 = 7^a % 97

    Finding the a using this code:
    ```bash
    for a in range(1,100):
        brute = (7**a) % 97
        print("(7**{}) % 97: {}".format(a, brute))
        if brute == 53:
            break
    ```
    > (7**22) % 97: 53\
    > a = 22

### Bob sent Alice the number 82
1. B = g^b % p
2. B = 7^b % 97
3. 82 = 7^b % 97

    Finding the b using this code:
    ```bash
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

