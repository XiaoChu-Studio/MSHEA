# MSHEA
#### MSHEA-Combined with multiple encryption technologies, including symmetric encryption, asymmetric encryption, and hash functions, to provide higher security and complexity.
#### MSHEA——结合了多种加密技术，包括对称加密、非对称加密和哈希函数，以提供更高的安全性和复杂性。

High security: Combined with multiple encryption technologies, it increases the difficulty of cracking.

高安全性：结合多种加密技术，增加了破解的难度。

Hash verification ensures data integrity.

哈希验证确保数据完整性。

Symmetric encryption ensures the efficiency of encryption and decryption, while asymmetric encryption ensures the security of keys.

对称加密确保加密和解密的效率，而非对称加密确保密钥的安全性。

中文版 : README.md

----

1. Key generation stage
    - Generate a pair of asymmetric keys, public key (n,e) and private key (n,d), in a similar way as mentioned earlier.
    - Select a strong symmetric encryption algorithm (such as AES) and generate a random symmetric key k.
2. Hashing stage
    - Perform a hash operation on the plaintext using a secure hash function (such as SHA-256) to obtain the hash value h.
3. Symmetric encryption stage
    - Encrypt the plaintext using the symmetric key k to obtain the preliminary ciphertext c1.
4. Asymmetric encryption stage
    - Concatenate the symmetric key k and the hash value h to obtain a combined data block dk.
    - Encrypt dk using the asymmetric public key (n,e) to obtain the ciphertext c2.
5. Final ciphertext generation stage
    - Concatenate the ciphertexts c1 and c2 to obtain the final ciphertext c.
----
1. Ciphertext separation stage
    - Separate the received ciphertext c into c1 and c2.
2. Asymmetric decryption stage
    - Decrypt c2 using the asymmetric private key (n,d) to obtain the combined data block dk of the symmetric key k and the hash value h.
3. Symmetric key and hash value extraction stage
    - Separate the symmetric key k and the hash value h from dk.
4. Symmetric decryption stage
    - Decrypt c1 using the symmetric key k to obtain the preliminary plaintext p1.
5. Hash verification stage
    - Perform a hash operation on the preliminary plaintext p1 to obtain a new hash value h1.
    - Compare h1 and h. If they are consistent, it means the plaintext has not been tampered with and the decryption is successful.
----
1. Key management is still crucial. Both asymmetric keys and symmetric keys need to be properly stored.
2. The selected hash function and symmetric encryption algorithm need to have sufficient security and reliability.
3. In practical applications, the algorithm needs to be fully tested and optimized to ensure its performance and security.
