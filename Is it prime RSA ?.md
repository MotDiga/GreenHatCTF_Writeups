# Is it prime RSA ?

## Challenge Description

-   Name: Is it prime RSA ?
-   Points: 500
-   Description: "show me that you really know RSA"

## Tools and Techniques

-   Tools: any programming language (with big number lib)
-   Techniques: 
	- RSA math (modular arithmetic)
	- Euler's totient function (φ(n)) of a Prime number
	- Number to ASCII conversion

## Solution

1.  **Initial Approach**
    
    -   RSA is secure with n (from public key (n, e)) equale the product of 2 prime numbers, but not with n a prime number
    -   We could get the private key (n, d) by calculating the euler's totient function of n wich is easy with n a prime number
 
2.  **Detailed Solution**
    
    -   **Step 1**: Calculating φ(n) 
        -   n a prime number and φ(p) = p - 1, for p a prime number
        -   => φ(n) = n - 1
    -   **Step 2**: Calculating the d exponent form the private key (n, d)
        -   Using φ(n) = n - 1, e and n from the public key (n, e)
        -   d = e^(-1) mod φ(n) (using a special theorem (fermat little theorm) or a build in function like pow() in python)
    -   **Step 3**: Calculating the original message m
        -   m = c^d mod n, where c is the cipher message
        -   Turning the number m to an ASCII string, the flag !

## Flag:
`microCTF{YoU_reviSED_weLL_8a51cs_0F_rSa}`
