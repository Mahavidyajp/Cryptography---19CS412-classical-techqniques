# Cryptography---19CS412-classical-techqniques
# Caeser Cipher
Caeser Cipher using with different key values

# AIM:

To encrypt and decrypt the given message by using Ceaser Cipher encryption algorithm.


## DESIGN STEPS:

### Step 1:

Design of Caeser Cipher algorithnm 

### Step 2:

Implementation using C or pyhton code

### Step 3:

1.	In Ceaser Cipher each letter in the plaintext is replaced by a letter some fixed number of positions down the alphabet.
2.	For example, with a left shift of 3, D would be replaced by A, E would become B, and so on.
3.	The encryption can also be represented using modular arithmetic by first transforming the letters into numbers, according to the   
    scheme, A = 0, B = 1, Z = 25.
4.	Encryption of a letter x by a shift n can be described mathematically as,
                       En(x) = (x + n) mod26
5.	Decryption is performed similarly,
                       Dn (x)=(x - n) mod26


## PROGRAM:
PROGRAM:
CaearCipher.
```
#include <stdio.h>
#include <string.h>

void caesar_cipher(char* text, int shift, int mode) {
    if (mode == 2) { // Decryption mode
        shift = 26 - (shift % 26); // Adjust shift for decryption
    }

    for (int i = 0; text[i] != '\0'; ++i) {
        char ch = text[i];

        // Encrypt/Decrypt uppercase letters
        if (ch >= 'A' && ch <= 'Z') {
            ch = (ch - 'A' + shift) % 26 + 'A';
        }
        // Encrypt/Decrypt lowercase letters
        else if (ch >= 'a' && ch <= 'z') {
            ch = (ch - 'a' + shift) % 26 + 'a';
        }

        text[i] = ch;
    }
}

int main() {
    char text[100];
    int shift, choice;

    printf("Enter a string: ");
    fgets(text, sizeof(text), stdin);
    text[strcspn(text, "\n")] = '\0';  // Remove newline character

    printf("Enter shift amount: ");
    scanf("%d", &shift);

    printf("Choose an option (1 for encryption, 2 for decryption): ");
    scanf("%d", &choice);

    caesar_cipher(text, shift, choice);

    if (choice == 1)
        printf("Encrypted text: %s\n", text);
    else if (choice == 2)
        printf("Decrypted text: %s\n", text);

    return 0;
}

```

## OUTPUT:

![Screenshot 2024-09-06 182451](https://github.com/user-attachments/assets/039e9985-198c-4807-ba04-f50c3b566030)

![Screenshot 2024-09-06 182615](https://github.com/user-attachments/assets/374ec190-cece-4a1a-9ac9-ae3c81670935)



## RESULT:
The program is executed successfully
