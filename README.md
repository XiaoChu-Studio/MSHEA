# MSHEA
#### MSHEA-Combined with multiple encryption technologies, including symmetric encryption, asymmetric encryption, and hash functions, to provide higher security and complexity.
#### MSHEA——结合了多种加密技术，包括对称加密、非对称加密和哈希函数，以提供更高的安全性和复杂性。

High security: Combined with multiple encryption technologies, it increases the difficulty of cracking.

高安全性：结合多种加密技术，增加了破解的难度。

Hash verification ensures data integrity.

哈希验证确保数据完整性。

Symmetric encryption ensures the efficiency of encryption and decryption, while asymmetric encryption ensures the security of keys.

对称加密确保加密和解密的效率，而非对称加密确保密钥的安全性。

English version : README-EN.md

----

1. 密钥生成阶段
 
- 生成一对非对称密钥，公钥（n,e）和私钥（n,d），方法与前面提到的类似。
- 选择一个强对称加密算法（如 AES），生成一个随机的对称密钥 k。
2. 哈希阶段
 
- 对明文进行哈希运算，使用安全的哈希函数（如 SHA-256），得到哈希值 h。
3. 对称加密阶段
 
- 使用对称密钥 k 对明文进行加密，得到初步密文 c1。
4. 非对称加密阶段
 
- 将对称密钥 k 与哈希值 h 拼接起来，得到一个组合数据块 dk。
- 使用非对称公钥（n,e）对 dk 进行加密，得到密文 c2。
5. 最终密文生成阶段
 
- 将密文 c1 和 c2 拼接起来，得到最终的密文 c。

----
1. 分离密文阶段
 
- 将接收到的密文 c 分离为 c1 和 c2。
2. 非对称解密阶段
 
- 使用非对称私钥（n,d）对 c2 进行解密，得到对称密钥 k 和哈希值 h 的组合数据块 dk。
3. 提取对称密钥和哈希值阶段
 
- 从 dk 中分离出对称密钥 k 和哈希值 h。
4. 对称解密阶段
 
- 使用对称密钥 k 对 c1 进行解密，得到初步明文 p1。
5. 哈希验证阶段
 
- 对初步明文 p1 进行哈希运算，得到新的哈希值 h1。
- 比较 h1 和 h，如果一致，则说明明文未被篡改，解密成功。

----
1. 密钥的管理仍然至关重要，非对称密钥和对称密钥都需要妥善保存。
2. 选择的哈希函数和对称加密算法需要具有足够的安全性和可靠性。
3. 在实际应用中，需要对算法进行充分的测试和优化，以确保其性能和安全性。

 

