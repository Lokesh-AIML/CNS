## EX. NO: 1 : IMPLEMENTATION OF CAESAR CIPHER
 

## AIM:

To implement the simple substitution technique named Caesar cipher using C language.

## DESCRIPTION:

To encrypt a message with a Caesar cipher, each letter in the message is changed using a simple rule: shift by three. Each letter is replaced by the letter three letters ahead in the alphabet. A becomes D, B becomes E, and so on. For the last letters, we can think of the
alphabet as a circle and "wrap around". W becomes Z, X becomes A, Y bec mes B, and Z
becomes C. To change a message back, each letter is replaced by the one three before it.

## EXAMPLE:



![image](https://github.com/Hemamanigandan/CNS/assets/149653568/eb9c6c43-8c80-4cdd-b9d4-91705a311c79)


## ALGORITHM:

### STEP-1: Read the plain text from the user.
### STEP-2: Read the key value from the user.
### STEP-3: If the key is positive then encrypt the text by adding the key with each character in the plain text.
### STEP-4: Else subtract the key from the plain text.
### STEP-5: Display the cipher text obtained above.


PROGRAM :-

```
Developed By : Lokeshwaran S
Registration Number : 212224240080


#include<stdio.h>
#include<stdlib.h>
#include<ctype.h>
void encrypt(char a[] , int key)
{
    for(int i = 0 ; a[i] != '\0' ; i++)
    {
        char ch = a[i];
        if(isalpha(ch))
        {
            char base = isupper(ch) ? 'A' : 'a';
            a[i] = (ch - base + key) % 26 + base;
        }
    }
}
void decrypt(char a[] , int key)
{
    for(int i = 0 ; a[i] != '\0' ; i++)
    {
        char ch = a[i];
        if(isalpha(ch))
        {
            char base = isupper(ch) ? 'A' : 'a';
            a[i] = (ch - base - key + 26) % 26 + base;
        }
    }
}
int main()
{
    char a[100];
    int key,choice;
    printf("Enter the text to encrypt or decrypt : ");
    fgets(a,100,stdin);
    printf("Enter the key : ");
    scanf("%d",&key);
    encrypt(a,key);
    printf("Encrypted text : %s",a);
    decrypt(a,key);
    printf("Decrypted text : %s",a);
}

```

OUTPUT :-

<img width="634" height="317" alt="image" src="https://github.com/user-attachments/assets/f5084497-90ee-44fd-9010-4e51cf041bbb" />

