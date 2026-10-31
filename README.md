# Lab-Exercise---3---Hill-Cipher
# Aim
To develop a simple C program to implement Hill
# Procedure
Design of Hill Cipher
Implementation using C or python code
Testing algorithm with different key values. ALGORITHM DESCRIPTION: The Hill cipher is a substitution cipher invented by Lester S. Hill in 1929. Each letter is represented by a number modulo 26.
To encrypt a message, each block of n letters is multiplied by an invertible n × n matrix, again modulus 26.
To decrypt the message, each block is multiplied by the inverse of the matrix used for encryption.
The matrix used for encryption is the cipher key, and it should be chosen randomly from the set of invertible n × n matrices (modulo 26).
The cipher can, be adapted to an alphabet with any number of letters.
All arithmetic just needs to be done modulo the number of letters instead of modulo.
# Program 
```
def encrypt(message, key):

    message = message.upper()

    # Add X if message length is odd
    if len(message) % 2 != 0:
        message += 'X'

    result = ""

    for i in range(0, len(message), 2):

        a = ord(message[i]) - ord('A')
        b = ord(message[i + 1]) - ord('A')

        c1 = (key[0][0] * a + key[0][1] * b) % 26
        c2 = (key[1][0] * a + key[1][1] * b) % 26

        result += chr(c1 + ord('A'))
        result += chr(c2 + ord('A'))

    return result


# Key matrix
key = [[3, 3],
       [2, 5]]

message = input("Enter message: ")

print("Encrypted message:", encrypt(message, key))
```
# Output
<img width="1362" height="612" alt="Screenshot 2026-10-26 103943" src="https://github.com/user-attachments/assets/76a7d7bf-aa64-4249-b3d5-590c401198f0" />

# Result
The program is executed successfully.
