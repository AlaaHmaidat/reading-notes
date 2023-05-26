# Cryptography


### What is the basic principle behind the Caesar Cipher, and how was it used historically?
The Caesar cipher is a simple encryption technique that was used by Julius Caesar to send secret messages to his military commanders.He would use a shift of 3, so 'A' would become 'D', 'B' would become 'E', and so on.  (It works by shifting the letters in the plaintext message by a certain number of positions, known as the “shift” or “key”).

The Caesar Cipher technique is one of the earliest and simplest methods of encryption technique. It’s simply a type of substitution cipher, i.e., each letter of a given text is replaced by a letter with a fixed number of positions down the alphabet. For example with a shift of 1, A would be replaced by B, B would become C, and so on. The method is apparently named after Julius Caesar, who apparently used it to communicate with his officials.

### What are the key differences between symmetric and asymmetric encryption? How is asymmetric used in secure communication today?
#### Symmetric
Symmetric Cryptography, likely the most traditional form of cryptography, is also the system with which you are probably most familiar.  

This type of cryptography uses a single key to encrypt a message and then decrypt that message upon delivery.

#### Asymmetric
Asymmetric cryptography (as the name suggests) uses two different keys for encryption and decryption, as opposed to the single key used in symmetric cryptography.

The first key is a public key used to encrypt a message, and the second is a private key which is used to decrypt them. The great part about this system is that only the private key can be used to decrypt encrypted messages sent from a public key.
asymmetric encryption plays a critical role in ensuring secure and private communication, providing key exchange mechanisms, digital signatures, and enabling secure protocols and infrastructures.

| Symmetric Key Encryption                            | Asymmetric Key Encryption                      |
|----------------------------------------------------|------------------------------------------------|
| It only requires a single key for both encryption and decryption. | It requires two keys, a public key and a private key, one to encrypt and the other one to decrypt. |
| The size of the cipher text is the same or smaller than the original plain text. | The size of the cipher text is the same or larger than the original plain text. |
| The encryption process is very fast.                | The encryption process is slow.                  |
| It is used when a large amount of data is required to transfer. | It is used to transfer small amounts of data.  |
| It only provides confidentiality.                   | It provides confidentiality, authenticity, and non-repudiation. |
| The length of the key used is 128 or 256 bits.      | The length of the key used is 2048 or higher.    |
| In symmetric key encryption, resource utilization is low as compared to asymmetric key encryption. | In asymmetric key encryption, resource utilization is high. |
| It is efficient as it is used for handling a large amount of data. | It is comparatively less efficient as it can handle a small amount of data. |
| Security is less as only one key is used for both encryption and decryption purposes. | It is more secure as two keys are used here - one for encryption and the other for decryption. |
| Examples: 3DES, AES, DES, and RC4                  | Examples: Diffie-Hellman, ECC, El Gamal, DSA, and RSA |

### How do computers generate random numbers, and what are the differences between true random number generation (TRNG) and pseudo-random number generation (PRNG)? Discuss their use cases in cryptography.
Random numbers in computer science is used for cryptography, simulation, sampling, design and games. In the past the need for more and more randomness has increased. Developers seek for more and more randomness. This project is based on generating random numbers using simple programming on a local system.

Computers generate random numbers using two main methods: true random number generation (TRNG) and pseudo-random number generation (PRNG).

1. True Random Number Generation (TRNG):
TRNG generates random numbers based on physical processes that are inherently unpredictable. It relies on capturing unpredictable data from sources such as atmospheric noise, radioactive decay, or mouse movements. These sources provide a continuous stream of random and unbiased data. TRNGs extract this randomness and convert it into random numbers. Since the sources are truly random, the generated numbers are considered to be genuinely unpredictable.

Use cases in cryptography: TRNGs are crucial in cryptographic applications where high-security requirements are necessary. They are used for generating random encryption keys, initialization vectors, nonces, and other critical values. TRNGs provide the highest level of randomness and are preferred when absolute unpredictability is essential.

2. Pseudo-Random Number Generation (PRNG):
PRNG generates random numbers using deterministic algorithms. These algorithms start with an initial seed value and use mathematical formulas to generate a sequence of numbers. The generated sequence appears random, but it is deterministic and repeatable if the same seed value is used. PRNGs do not rely on true randomness but instead create the illusion of randomness.

Use cases in cryptography: PRNGs are commonly used in various cryptographic applications. They are used for generating random session keys, generating random padding for encryption algorithms, and creating random challenges for authentication protocols. PRNGs are generally faster and more efficient than TRNGs, making them suitable for applications where true randomness is not critical but sufficient randomness is required.


### What’s the difference between encryption and decryption? Explain with an analogy.
Encryption and decryption are two fundamental processes in cryptography.

Encryption can be likened to placing a message inside a locked safe. It involves transforming the original message (plaintext) into an unreadable and scrambled form (ciphertext) using an encryption algorithm and a secret key. This process ensures that unauthorized individuals cannot understand or access the information without the corresponding key.

On the other hand, decryption is like using the key to unlock the safe and retrieve the original message. It is the process of reversing encryption by applying a decryption algorithm and the correct key to transform the ciphertext back into its original plaintext form. Decryption allows authorized individuals to access and comprehend the message securely.

In summary, encryption is the process of transforming plaintext into ciphertext to protect sensitive information, while decryption is the reverse process of converting ciphertext back into plaintext using the appropriate key. Together, encryption and decryption form the basis of secure communication and data protection.

### How can i encrypt passwords in python
You can encrypt passwords using various cryptographic algorithms and libraries. One commonly used library is `bcrypt`, which provides a secure and robust method for password encryption. Here's an example of how you can encrypt a password using bcrypt:

```python
import bcrypt

password = "my_password".encode('utf-8')

# Generate a salt
salt = bcrypt.gensalt()

# Hash the password with the salt
hashed_password = bcrypt.hashpw(password, salt)

# Print the hashed password
print(hashed_password)
```
#### Note: The resulting hashed password can be stored in a database or file for later verification.

To verify a password against the stored hashed password, you can use the bcrypt.checkpw() function:
```python
stored_password = hashed_password  # Retrieve the stored hashed password from the database

input_password = "my_password".encode('utf-8')

# Check if the input password matches the stored hashed password
if bcrypt.checkpw(input_password, stored_password):
    print("Password is correct.")
else:
    print("Password is incorrect.")
```
The bcrypt.checkpw() function compares the input password with the stored hashed password and returns True if they match, indicating that the provided password is correct.

### *Resources:*
[Encryption, Decryption & Hacking](https://www.khanacademy.org/computing/computers-and-internet/xcae6f4a7ff015e7d:online-data-security/xcae6f4a7ff015e7d:data-encryption-techniques/a/encryption-decryption-and-code-cracking)

[Ceasar Cipher](https://en.wikipedia.org/wiki/Caesar_cipher)

[Cryptography Crash Course](https://www.youtube.com/watch?v=jhXCTbFnK8o)

[Introduction to Cryptography](https://thebestvpn.com/cryptography/)

[How Computers Generate Random Numbers](https://www.howtogeek.com/183051/htg-explains-how-computers-generate-random-numbers/)

## Things I want to know more about