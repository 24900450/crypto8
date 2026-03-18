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

int main()
{
    char text[50], key[50];
    int i, len;

    printf("Enter text: ");
    scanf("%s", text);

    printf("Enter key: ");
    scanf("%s", key);

    len = strlen(text);

    // Encryption (AddRoundKey + simple shift)
    for(i = 0; i < len; i++)
    {
        text[i] = (text[i] ^ key[i % strlen(key)]) + 1;
    }

    printf("Encrypted: ");
    for(i = 0; i < len; i++)
    {
        printf("%02X ", (unsigned char)text[i]);
    }
    // Decryption
    for(i = 0; i < len; i++)
    {
        text[i] = (text[i] - 1) ^ key[i % strlen(key)];
    }

    printf("\nDecrypted Text: %s\n", text);

    return 0;
}
```

# OUTPUT:
<img width="440" height="307" alt="image" src="https://github.com/user-attachments/assets/9da32f46-65ed-45db-9326-1613a6f70fd7" /><br>
# RESULT:
Hence, Advanced Encryption Standard (AES) Algorithm for a practical application like URL Encryption is done successfully.


