
# Cryptography

## Data Encryption Standard (DES)

* Data Encryption Standard (DES) is a symmetric key block cipher algorithm.

* Developed by IBM in the 1970s and later adopted as a federal standard in the United States.

* Operates on fixed-size blocks of plaintext(`64 bits`).

* Uses a `56-bit` encryption key.

* Consists of several rounds of operations: substitution, permutation, and XOR.

* Encryption and decryption processes use the same key (symmetric key).

## Advanced Encryption Standard (AES)

* `Symmetric Encryption:` AES is a symmetric encryption algorithm, meaning the same key is used for both encryption and decryption processes.

* `Block Cipher:` AES operates on fixed-size blocks of data, with a block size of 128 bits (16 bytes). The data to be encrypted is divided into blocks, and each block is processed independently.

* `Key Sizes:` AES supports three different key sizes: 128 bits, 192 bits, and 256 bits. The longer the key size, the stronger the encryption.

* `Selected Standard:` In 2001, AES was selected by the U.S. National Institute of Standards and Technology (NIST) as the replacement for the older Data Encryption Standard (DES). It became the standard encryption algorithm for government and commercial applications.

* `Cryptographic Transformations:` AES employs a series of cryptographic transformations to encrypt and decrypt data. These transformations include byte substitution, shifting rows, mixing columns, and adding a round key.

* `Rounds:` AES performs a specific number of rounds based on the key size. AES-128 uses 10 rounds, AES-192 uses 12 rounds, and AES-256 uses 14 rounds. Each round applies a set of operations to the data, providing additional security.

* `Security and Analysis:` AES has been extensively analyzed by cryptographers worldwide and is considered secure. Its strength is based on the complexity of its transformations and the key length used.

* `Efficiency:` AES is efficient in both software and hardware implementations. It can be effectively used in various computing environments, ranging from personal computers to embedded systems.

* `Applications:` AES is widely used to secure sensitive data in various applications, including secure communications (such as SSL/TLS), file encryption, database encryption, secure storage devices, and more.

* `Key Management:` Secure key management is crucial in AES. The security of encrypted data relies on keeping the encryption key secret and properly managing its distribution and storage.

## 1.png

![App Screenshot](https://via.placeholder.com/468x300?text=App+Screenshot+Here)

-------------------------------------------------------

## RC4, RC5, and RC6 Algorithms

RC4, RC5, and RC6 are symmetric encryption algorithms developed by `Ron Rivest`, a cryptographer and co-founder of RSA Security. While they are all part of the RC (Rivest Cipher) series, each algorithm has its own characteristics and features. Here's an overview of each algorithm:

### 1. RC4 (Rivest Cipher 4):
   - RC4 is a stream cipher, which means it encrypts data on a byte-by-byte basis.
   - It uses a variable-length key (ranging from 1 to 256 bytes) to generate a pseudorandom keystream.
   - The keystream is then XORed with the plaintext to produce the ciphertext.
   - RC4 gained popularity due to its simplicity and speed. It has been widely used in protocols such as WEP (Wired Equivalent Privacy) for wireless networks and SSL/TLS for secure communications.
   - However, vulnerabilities and weaknesses have been discovered in RC4, leading to its gradual deprecation in recent years.

### 2. RC5 (Rivest Cipher 5):
   - RC5 is a block cipher that operates on fixed-size data blocks.
   - It supports variable block sizes (32, 64, or 128 bits) and key sizes (up to 2040 bits).
   - RC5 uses a Feistel network structure, which involves multiple rounds of operations to encrypt or decrypt data.
   - The key feature of RC5 is its parameterized design, allowing flexibility in block and key sizes, as well as the number of rounds.
   - RC5 gained attention for its simplicity and ability to adapt to different security requirements. However, it has not gained widespread adoption compared to other algorithms like AES.

### 3. RC6 (Rivest Cipher 6):
   - RC6 is an extension of RC5 and is also a block cipher.
   - It maintains the parameterized design of RC5, allowing customization of block sizes, key sizes, and rounds.
   - RC6 uses a combination of bitwise operations (such as modular addition, rotation, and XOR) to perform encryption and decryption.
   - It is designed to offer improved security and performance compared to RC5.
   - RC6 has not been widely adopted in commercial applications, and its usage is less prevalent compared to AES and other modern encryption algorithms.

It's worth noting that while RC4, RC5, and RC6 were developed by `Ron Rivest`, they have not received the same level of scrutiny, analysis, and widespread adoption as the `AES algorithm`. AES is currently considered the industry standard for symmetric encryption due to its proven security, extensive analysis, and wide support across various systems and platforms.

## 2.png

![App Screenshot](https://via.placeholder.com/468x300?text=App+Screenshot+Here)

## Blowfish

Blowfish is a `symmetric encryption algorithm` designed by `Bruce Schneier` in 1993. It is a block cipher that operates on fixed-size blocks of data. Blowfish is known for its simplicity, speed, and flexibility.

Key features of the Blowfish algorithm include:

1. Variable Key Size: Blowfish supports key sizes from `32 bits to 448 bits`, making it adaptable to different security requirements.

2. Feistel Network Structure: Blowfish employs a Feistel network structure, which involves multiple rounds of operations to encrypt or decrypt data. It uses a modified version of the Feistel network to ensure security and resistance against various cryptographic attacks.

3. Block Size: The block size of Blowfish is `64 bits`, meaning data is processed in `64-bit` blocks during encryption and decryption.

4. Subkey Generation: Blowfish generates a series of subkeys from the original encryption key using a `key expansion algorithm`. These subkeys are used in the encryption and decryption processes.

5. Multiple Rounds: Blowfish uses a variable number of rounds depending on the key size chosen. The number of rounds can range from `16 to 72`.

6. Operations: Blowfish utilizes a combination of simple operations such as `substitution, permutation, XOR, and modular addition` to encrypt and decrypt data.

Blowfish has gained popularity due to its `speed and efficiency`, especially in software implementations. It has been widely used in various applications, including encryption of files, secure communication protocols, and password hashing.

However, it's important to note that Blowfish is now considered to have `weaker security` compared to more modern encryption algorithms such as AES. While Blowfish is still considered secure for most applications, it has not undergone the same level of scrutiny and analysis as AES. As a result, it is generally recommended to use AES or other modern encryption algorithms for new cryptographic implementations.

-------------------------------------------------------

## Twofish and Threefish

Twofish and Threefish are symmetric encryption algorithms designed by Bruce Schneier and his team as part of the Skein cryptographic hash function project. Although they share similarities in their names, they are separate algorithms with different purposes. Here's an overview of each algorithm:

## 1. Twofish:
   - Twofish is a symmetric block cipher designed to be highly secure and flexible.
   - It supports block sizes of `128 bits` and key sizes of `128, 192, or 256 bits`.
   - Twofish employs a `Feistel network structure` with a variable number of rounds (typically 16) based on the key size.
   - The algorithm uses a combination of substitutions, permutations, and key-dependent operations to encrypt and decrypt data.
   - Twofish was one of the finalists in the AES competition, where it competed against Rijndael (which became AES). While it did not become the standard, it is still considered a strong encryption algorithm.

## 2. Threefish:
   - Threefish is a `symmetric tweakable block cipher` primarily designed for use in `cryptographic hash functions`, such as the Skein hash function.
   - It supports block sizes of `256, 512, or 1024 bits`.
   - Threefish uses a generalized `Feistel structure` and incorporates a tweak value along with the key and plaintext to generate the ciphertext.
   - The tweak value allows for additional customization and security in applications where the same key is used multiple times.
   - Threefish is designed to be secure against various attacks, including differential and linear cryptanalysis.
   - It is used as a component in the `Skein hash function`, which was a candidate in the NIST hash function competition.

Both Twofish and Threefish are considered strong encryption algorithms, offering high levels of security. However, it's important to note that their usage is less widespread compared to established algorithms like AES. Their adoption is mainly seen in specific applications or research contexts where their specific features and properties are advantageous.

## 3.png

![App Screenshot](https://via.placeholder.com/468x300?text=App+Screenshot+Here)

-------------------------------------------------------

## Serpent and TEA

Serpent and TEA (Tiny Encryption Algorithm) are two different symmetric encryption algorithms with distinct characteristics and purposes. Here's an overview of each algorithm:

## 1. Serpent:
   - Serpent is a symmetric key block cipher designed by Ross Anderson, Eli Biham, and Lars Knudsen.
   - It was one of the candidates in the AES competition and is known for its security and strong resistance against various cryptographic attacks.
   - Serpent supports block sizes of 128 bits and key sizes of 128, 192, or 256 bits.
   - The algorithm uses a substitution-permutation network (SPN) structure with multiple rounds (32 rounds in total).
   - Serpent incorporates a combination of bitwise operations, substitutions, permutations, and key-dependent operations to encrypt and decrypt data.
   - It is considered to have a conservative design, prioritizing security over performance.
   - Although Serpent did not become the AES standard, it is recognized as a secure encryption algorithm and is still used in various applications where its features and properties are beneficial.

## 2. TEA (Tiny Encryption Algorithm):
   - TEA, also known as the Tiny Encryption Algorithm, is a symmetric block cipher designed by David Wheeler and Roger Needham.
   - TEA operates on 64-bit blocks of data and uses a 128-bit key.
   - It is known for its simplicity and compactness, with the entire algorithm consisting of only a few lines of code.
   - TEA employs a Feistel network structure with a total of 64 rounds.
   - The algorithm uses simple bitwise XOR and addition operations combined with bitwise shifts to perform encryption and decryption.
   - TEA is mainly designed for low-resource systems and applications where code size and execution speed are critical.
   - However, it's important to note that TEA is considered to have certain vulnerabilities and weaknesses when compared to more modern encryption algorithms. As a result, it is generally not recommended for new cryptographic implementations.

Both Serpent and TEA have their specific strengths and applications. Serpent is favored for its security and resistance against attacks, while TEA is valued for its simplicity and suitability for constrained environments. However, it's essential to consider more widely adopted and analyzed algorithms like AES for most encryption needs.

## 4.png

![App Screenshot](https://via.placeholder.com/468x300?text=App+Screenshot+Here)

-------------------------------------------------------

## CAST-128

CAST-128, also known as CAST5, is a symmetric encryption algorithm designed by Carlisle Adams and Stafford Tavares. CAST stands for "Carlisle Adams and Stafford Tavares." CAST-128 is a block cipher that operates on fixed-size blocks of data.

Key features of CAST-128 include:

1. Block Size and Key Size: CAST-128 uses a block size of 64 bits and supports key sizes ranging from 40 to 128 bits.

2. Feistel Network Structure: CAST-128 employs a Feistel network structure, which involves multiple rounds of operations to encrypt or decrypt data.

3. Rounds and Subkeys: CAST-128 uses 12 rounds of operations. It generates a set of 16 subkeys derived from the original encryption key to be used in the encryption and decryption processes.

4. Operations: CAST-128 incorporates a combination of substitution, permutation, and bitwise XOR operations to provide data encryption and decryption.

5. Known for Efficiency: CAST-128 is known for its efficiency, especially in software implementations. It can be implemented with relatively low computational overhead and has been widely used in software applications.

6. Security: CAST-128 is considered to have a good security level and has undergone significant analysis by the cryptographic community. However, it has been deprecated as a recommended algorithm by NIST due to its relatively smaller block size compared to more modern encryption algorithms.

It's worth noting that while CAST-128 was widely used in the past, it has been largely replaced by more secure and efficient algorithms like AES. AES has become the industry standard for symmetric encryption due to its higher security level, extensive analysis, and wide support across various platforms and systems.

## 5.png

![App Screenshot](https://via.placeholder.com/468x300?text=App+Screenshot+Here)

-------------------------------------------------------

## GOST Block Cipher and Camellia

GOST Block Cipher and Camellia are two distinct symmetric encryption algorithms with different origins and characteristics. Here's an overview of each algorithm:

## 1. GOST Block Cipher:
   - GOST Block Cipher, also known as `GOST 28147-89`, is a `symmetric encryption` algorithm developed by the `Soviet Union` in 1989.
   - It is a block cipher that operates on `64-bit` blocks of data and supports a key size of 256 bits.
   - GOST Block Cipher uses a `Feistel network structure` with `32 rounds` of operations.
   - The algorithm employs a combination of bitwise operations, substitutions, and permutations to provide encryption and decryption.
   - GOST Block Cipher gained wide usage in `Russia` and some other countries, primarily for government and military applications.
   - It has undergone analysis and scrutiny by the cryptographic community and is generally considered to have a good security level. However, it has not received as much international scrutiny and analysis as widely adopted algorithms like AES.

## 2. Camellia:
   - Camellia is a `symmetric encryption` algorithm jointly developed by `NTT (Nippon Telegraph and Telephone Corporation) of Japan and Mitsubishi Electric in 2000`.
   - It is a block cipher that operates on `128-bit` blocks of data and supports key sizes of `128, 192, or 256 bits`.
   - Camellia uses a `Feistel network structure` with up to `18 rounds` of operations, depending on the key size.
   - The algorithm incorporates a combination of substitution, permutation, and bitwise XOR operations for encryption and decryption.
   - Camellia was designed as a candidate for the AES selection process, demonstrating its high security and performance characteristics.
   - Although it did not become the selected AES algorithm, Camellia is widely recognized as a strong and secure encryption algorithm. It has been adopted in various applications and protocols, particularly in Japan and some other countries.

Both GOST Block Cipher and Camellia are symmetric encryption algorithms that have been subjected to analysis and evaluation. While GOST Block Cipher is more commonly used in Russia and some other countries, Camellia has gained wider international recognition and adoption. It's important to note that the selection of an encryption algorithm depends on specific security requirements, standards compliance, and industry practices.

## 6.png

![App Screenshot](https://via.placeholder.com/468x300?text=App+Screenshot+Here)

-------------------------------------------------------

## DSA and Related Signature Schemes

DSA stands for Digital Signature Algorithm. It is a widely used cryptographic algorithm for generating digital signatures, which are used to ensure the authenticity, integrity, and non-repudiation of digital documents or messages.

The DSA algorithm is based on the mathematical concept of modular exponentiation and relies on the computational difficulty of the discrete logarithm problem in finite fields. DSA has been standardized by the National Institute of Standards and Technology (NIST) in the United States.

DSA involves the use of a public-private key pair. The private key is kept secret by the signer and is used to generate the digital signature, while the corresponding public key is made publicly available for verification of the signature. The digital signature provides a way to prove that the message was signed by the holder of the private key and that it has not been tampered with since the signature was generated.

There are a few related signature schemes based on the DSA algorithm. These include:

### 1. ECDSA (Elliptic Curve Digital Signature Algorithm): 
ECDSA is a variant of DSA that uses elliptic curve cryptography instead of modular exponentiation. It offers the same security level as DSA but with shorter key sizes, making it more efficient.

### 2. RSA (Rivest-Shamir-Adleman): 
Although RSA is not directly related to DSA, it is another widely used signature scheme. RSA signatures are based on the computational difficulty of factoring large composite numbers. RSA signatures offer similar security guarantees as DSA but have different mathematical foundations.

### 3. EdDSA (Edwards-curve Digital Signature Algorithm): 
EdDSA is a modern digital signature scheme based on elliptic curve cryptography. It provides high security levels and improved performance compared to traditional DSA and ECDSA.

These signature schemes serve the same purpose of ensuring the authenticity and integrity of digital data, but they differ in their underlying mathematics, security levels, and performance characteristics. The choice of which signature scheme to use depends on factors such as security requirements, key size, computational resources, and compatibility with existing systems and standards.

## 7.png

![App Screenshot](https://via.placeholder.com/468x300?text=App+Screenshot+Here)

-------------------------------------------------------

## Rivest Shamir Adleman (RSA)

RSA, which stands for `Rivest-Shamir-Adleman`, is one of the most widely used and influential cryptographic algorithms. It is named after its inventors, `Ron Rivest, Adi Shamir, and Leonard Adleman`, who introduced it in 1977. RSA is an `asymmetric encryption algorithm` that relies on the computational difficulty of factoring large composite numbers.

The RSA algorithm involves the use of a `public-private key pair`. The `private key` is kept secret by the owner and is used for `decrypting or signing data`, while the corresponding public key is made publicly available for `encryption or signature verification`.

Here is a brief overview of how RSA works:

1. Key Generation: The first step in RSA is to generate a key pair. This involves selecting two large prime numbers, p and q, calculating their product n = p * q, and selecting a public exponent e. The private key consists of the prime factors p and q, as well as a secret exponent d.

2. Encryption: To encrypt a message using RSA, the sender applies the recipient's public key (n, e) to the plaintext message. This is done by raising the plaintext to the power of e and taking the modulus n, resulting in the ciphertext.

3. Decryption: To decrypt the ciphertext, the recipient uses their private key (p, q, d). They raise the ciphertext to the power of d and take the modulus n, which recovers the original plaintext message.

4. Digital Signatures: RSA can also be used for digital signatures. To create a signature, the signer applies their private key to a hash of the message, producing a signature. The signature can be verified by anyone using the signer's public key and comparing it to a recalculated hash of the message.

The security of RSA is based on the difficulty of factoring large composite numbers into their prime factors. As long as factoring large numbers remains computationally expensive, RSA is considered secure. However, with advances in computing power and the development of more efficient factoring algorithms, longer key sizes are needed to maintain the same level of security.

RSA has been widely adopted in various applications, including secure communications, digital signatures, secure key exchange, and encryption of sensitive data. Its versatility, mathematical elegance, and long-standing track record have made it a cornerstone of modern cryptography.

## 8.jpg

![App Screenshot](https://via.placeholder.com/468x300?text=App+Screenshot+Here)

-------------------------------------------------------

## Diffie-Hellman

Diffie-Hellman (DH) is a `key exchange protocol` that allows two parties to establish a shared secret key over an insecure communication channel. It was invented by `Whitfield Diffie and Martin Hellman` in 1976 and is one of the fundamental building blocks of modern cryptography.

The Diffie-Hellman protocol is based on the concept of `modular exponentiation and the computational difficulty of the discrete logarithm problem.` Here's a simplified explanation of how the protocol works:

1. Key Generation: Both parties, let's call them Alice and Bob, agree on a large prime number, p, and a base number, g. These values are public and known to both parties.

2. Private Key Selection: Alice chooses a secret integer, a, while Bob chooses a secret integer, b. These private keys are kept secret and not shared with anyone.

3. Public Key Exchange: Alice computes her public key by raising the base g to the power of her private key a, modulo p. Bob does the same by raising the base g to the power of his private key b, modulo p. Alice and Bob exchange their computed public keys.

4. Shared Secret Calculation: Alice takes Bob's public key and raises it to the power of her private key a, modulo p. Bob takes Alice's public key and raises it to the power of his private key b, modulo p. Both Alice and Bob end up with the same shared secret key.

5. Key Derivation: The shared secret key generated in the previous step can be used as a symmetric encryption key or any other purpose that requires a shared secret between Alice and Bob.

The security of the Diffie-Hellman protocol lies in the `difficulty of computing discrete logarithms`. While computing g^a modulo p and g^b modulo p is computationally efficient, computing the private key a or b from the corresponding public key is believed to be computationally infeasible, especially when `large prime numbers` are used.

Diffie-Hellman is often used in conjunction with other cryptographic algorithms, such as `symmetric encryption or digital signatures`, to establish secure communication channels and protect the confidentiality and integrity of data. It has been widely adopted and standardized in various protocols and systems, including `secure socket layer (SSL/TLS)` for secure web communication.

## 9.jpg

![App Screenshot](https://via.placeholder.com/468x300?text=App+Screenshot+Here)

-------------------------------------------------------

## YAK

YAK (Yet Another Key Exchange) is a public-key authenticated key-agreement protocol. It was proposed by Feng Hao in 2010 and is claimed to be the simplest authenticated key exchange protocol among the related schemes, including MQV, HMQV, Station-to-Station protocol, SSL/TLS etc. The authentication is based on public key pairs. As with other protocols, YAK normally requires a Public Key Infrastructure to distribute authentic public keys to the communicating parties.

The security of YAK is disputed. In 2020, Mohammad mentioned that YAK protocol cannot withstand the known key security attack which leads to a new key compromise impersonation attack where an adversary is allowed to reveal both the shared static secret key between two parties and the ephemeral private key of the initiator. The author also proposed an improved protocol to remedy these attacks and the previous attacks mentioned by Toorani on the YAK protocol, and the proposed protocol uses a verification mechanism that provides entity authentication and key confirmation.

The following is a summary of the YAK protocol:

Alice and Bob generate their own public/private key pairs.
Alice sends her public key to Bob.
Bob sends his public key to Alice.
Alice generates an ephemeral private key and computes an ephemeral public key.
Bob generates an ephemeral private key and computes an ephemeral public key.
Alice sends her ephemeral public key to Bob.
Bob sends his ephemeral public key to Alice.
Alice and Bob use their respective public keys to compute a shared secret key.
Alice and Bob use the shared secret key to encrypt and decrypt data.
The YAK protocol is a simple and efficient way to establish a secure connection between two parties. However, it is important to note that the security of YAK has been disputed. If you are using YAK, it is important to be aware of the potential attacks and to take steps to mitigate them.

## 10.jpg

![App Screenshot](https://via.placeholder.com/468x300?text=App+Screenshot+Here)

-------------------------------------------------------

## Message Digest (One-Way Hash) Functions

Message Digest Functions, also known as one-way hash functions, are cryptographic algorithms that take an input (or message) of arbitrary length and produce a fixed-size output, called a hash value or message digest. These functions have the following properties:

1. One-wayness: It is computationally infeasible to retrieve the original input message from the hash value. Given a hash value, it should be extremely difficult to find any message that produces the same hash value.

2. Determinism: The same input message will always produce the same hash value. This property allows for verification and comparison of hash values.

3. Fixed output size: The hash function produces a fixed-size output, regardless of the size of the input message. Common hash functions have output sizes such as 128 bits (MD5), 160 bits (SHA-1), 256 bits (SHA-256), or 512 bits (SHA-512).

4. Avalanche effect: A small change in the input message should result in a significantly different hash value. Even a tiny alteration in the input message should cause the resulting hash value to appear completely different.

5. Collision resistance: It should be computationally infeasible to find two different input messages that produce the same hash value. This property ensures that the hash function has a low probability of collision, where two different inputs produce the same hash output.

Message digest functions have numerous applications in information security, including password storage, data integrity verification, digital signatures, and secure data transmission. Commonly used hash functions include MD5, SHA-1, SHA-256, SHA-3, and Blake2. However, it is important to note that MD5 and SHA-1 are considered weak and are no longer recommended for security-sensitive applications due to vulnerabilities discovered over time. Stronger hash functions like SHA-256 and SHA-3 are widely used for cryptographic purposes today.

## 11.jpg

![App Screenshot](https://via.placeholder.com/468x300?text=App+Screenshot+Here)

-------------------------------------------------------

## Message Digest Function: MD5 and MD6

## 12.jpg

![App Screenshot](https://via.placeholder.com/468x300?text=App+Screenshot+Here)

-------------------------------------------------------

## Message Digest Function: Secure Hashing Algorithm (SHA)

## 13.jpg

![App Screenshot](https://via.placeholder.com/468x300?text=App+Screenshot+Here)

-------------------------------------------------------

## RIPEMD-160 and HMAC

**RIPEMD-160:**
RIPEMD-160 (RACE Integrity Primitives Evaluation Message Digest-160) is a cryptographic hash function that produces a fixed-size 160-bit hash value. It was developed by Hans Dobbertin, Antoon Bosselaers, and Bart Preneel as an improvement over the original RIPEMD algorithm.

RIPEMD-160 is often used in conjunction with other cryptographic algorithms, such as public key algorithms, for applications like digital signatures and data integrity checks. It offers a higher level of security compared to its predecessor RIPEMD, which had 128-bit output. RIPEMD-160 has been widely adopted and is particularly popular in Bitcoin and other cryptocurrencies as part of their address generation and transaction verification processes.

**HMAC (Hash-based Message Authentication Code):**
HMAC (Hash-based Message Authentication Code) is a specific construction that uses a cryptographic hash function along with a secret key to provide message integrity and authenticity. It was initially described by Mihir Bellare, Ran Canetti, and Hugo Krawczyk in 1996.

HMAC operates by taking an input message and applying a hash function (such as MD5, SHA-1, or SHA-256) to it in a specific way, involving the secret key. The resulting hash value, combined with the secret key again, creates the authentication code or tag. This tag is then appended to the original message or transmitted separately along with the message.

HMAC provides the following security properties:
1. Message integrity: It ensures that the message has not been altered during transit.
2. Authenticity: It verifies the identity of the sender by using the secret key.
3. Keyed hash function: The secret key adds an additional layer of security to the hash function, making it harder for an attacker to tamper with the message or generate a valid HMAC without knowledge of the key.

HMAC is widely used in various protocols and applications, such as network communications (e.g., IPsec, TLS/SSL), digital signatures, and password authentication systems. It provides a secure way to verify the integrity and authenticity of messages, even when transmitted over an insecure network.

## 14.jpg

![App Screenshot](https://via.placeholder.com/468x300?text=App+Screenshot+Here)


-------------------------------------------------------

## 15.jpg

![App Screenshot](https://via.placeholder.com/468x300?text=App+Screenshot+Here)

## 16.jpg

![App Screenshot](https://via.placeholder.com/468x300?text=App+Screenshot+Here)

## 17.jpg

![App Screenshot](https://via.placeholder.com/468x300?text=App+Screenshot+Here)

-------------------------------------------------------

## Comparison of Cryptographic Algorithms

## 18.jpg

![App Screenshot](https://via.placeholder.com/468x300?text=App+Screenshot+Here)
