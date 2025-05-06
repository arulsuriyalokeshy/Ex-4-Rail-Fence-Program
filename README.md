# Ex--5-Rail-Fence-Program

## AIM:

To write a python program to implement the rail fence transposition technique.

## DESCRIPTION:

In the rail fence cipher, the plain text is written downwards and diagonally on successive "rails" of an imaginary fence, then moving up when we reach the bottom rail. When we reach the top rail, the message is written downwards again until the whole plaintext is written out. The message is then read off in rows.

## ALGORITHM:

STEP-1: Read the Plain text.<br>
STEP-2: Arrange the plain text in row columnar matrix format.<br>
STEP-3: Now read the keyword depending on the number of columns of the plain text.<br>
STEP-4: Arrange the characters of the keyword in sorted order and the corresponding columns of the plain text.<br>
STEP-5: Read the characters row wise or column wise in the former order to get the cipher text.

## PROGRAM
```
def encrypt_rail_fence(text):
    even_chars = []
    odd_chars = []

    for i in range(len(text)):
        if i % 2 == 0:
            even_chars.append(text[i])
        else:
            odd_chars.append(text[i])

    cipher_text = ''.join(even_chars + odd_chars)
    return cipher_text


def decrypt_rail_fence(cipher_text):
    l = len(cipher_text)
    if l % 2 == 0:
        k = l // 2
    else:
        k = (l // 2) + 1

    decrypted = [''] * l
    index = 0

    # Fill even indices
    for i in range(k):
        decrypted[index] = cipher_text[i]
        index += 2

    # Fill odd indices
    index = 1
    for i in range(k, l):
        decrypted[index] = cipher_text[i]
        index += 2

    return ''.join(decrypted)


def main():
    print("\n\t\tRAIL FENCE TECHNIQUE")
    text = input("\nEnter the input string: ")

    cipher = encrypt_rail_fence(text)
    print("\nCipher text after applying rail fence:", cipher)

    decrypted = decrypt_rail_fence(cipher)
    print("\nText after decryption:", decrypted)


if __name__ == "__main__":
    main()

```
## OUTPUT
![image](https://github.com/user-attachments/assets/a5edfd5b-b4ab-414d-bb1f-7d894e560fc4)


## RESULT
The program is executed successfully

