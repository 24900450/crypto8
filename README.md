# EX-8-ADVANCED-ENCRYPTION-STANDARD ALGORITHM
# Aim:
To use Advanced Encryption Standard (AES) Algorithm for a practical application like URL Encryption.

# ALGORITHM:
AES is based on a design principle known as a substitution–permutation.
AES does not use a Feistel network like DES, it uses variant of Rijndael.
It has a fixed block size of 128 bits, and a key size of 128, 192, or 256 bits.
AES operates on a 4 × 4 column-major order array of bytes, termed the state
# PROGRAM:
```c
#include <stdio.h> 
#include <string.h> 

void simpleAESEncrypt(char *plaintext, char *key, char *ciphertext) 
{
    int i; 
    for (i = 0; i < strlen(plaintext); i++) 
    { 
        ciphertext[i] = plaintext[i] ^ key[i % strlen(key)]; 
    } 
    ciphertext[i] = '\0'; 
} 

void simpleAESDecrypt(char *ciphertext, char *key, char *decryptedText) 
{ 
    int i; 
    for (i = 0; i < strlen(ciphertext); i++) 
    {                                                                
        decryptedText[i] = ciphertext[i] ^ key[i % strlen(key)]; 
    } 
    decryptedText[i] = '\0'; 
} 

void printASCII(char *ciphertext) 
{ 
    printf("Encrypted Message (ASCII values): "); 
    for (int i = 0; i < strlen(ciphertext); i++) 
    { 
        printf("%d ", (unsigned char)ciphertext[i]); 
    } 
    printf("\n"); 
} 

int main() 
{ 
    char plaintext[100], key[100], ciphertext[100], decryptedText[100]; 

    printf("Enter the plaintext: "); 
    scanf("%s", plaintext); 

    printf("Enter the key: ");  
    scanf("%s", key);  

    simpleAESEncrypt(plaintext, key, ciphertext); 
    printASCII(ciphertext);  

    simpleAESDecrypt(ciphertext, key, decryptedText); 
    printf("Decrypted Message: %s\n", decryptedText); 

    return 0; 
}
```

# OUTPUT:
<img width="677" height="302" alt="image" src="https://github.com/user-attachments/assets/f1a1dccb-1d10-47f1-bd51-316902981c90" /><br>
# RESULT:
Hence, Advanced Encryption Standard (AES) Algorithm for a practical application like URL Encryption is done successfully.


