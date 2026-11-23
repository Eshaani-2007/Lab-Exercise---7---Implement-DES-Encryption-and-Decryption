# Lab-Exercise---7---Implement-DES-Encryption-and-Decryption
**Aim:**

To use the Data Encryption Standard(DES) algorithm for a practical application, such as securing sensitive data transmission in financial transactions.

**Procedure:**

DES is based on a symmetric key encryption technique that encrypts data in 64-bit blocks. DES uses a Feistel network structure with 16 rounds of processing for encryption. DES has a 64-bit key, but only 56 bits are used for encryption(the remaining 8 bits are for parity) DES applies initial and final permutations along with 16 rounds of substitution and permutation transformations to produce ciphertext.

**Program:**

```
from Crypto.Cipher import DES
from Crypto.Util.Padding import pad, unpad

key = b'12345678'
cipher = DES.new(key, DES.MODE_ECB)

text = b'HelloDES!'

**# PKCS7 padding**
padded_text = pad(text, 8)

**# Encryption**
encrypted = cipher.encrypt(padded_text)

**# Decryption**
decrypted_padded = cipher.decrypt(encrypted)
decrypted = unpad(decrypted_padded, 8)

print("Original:", text)
print("Encrypted:", encrypted)
print("Decrypted:", decrypted)
```

**OUTPUT**
<img width="992" height="597" alt="WhatsApp Image 2026-11-23 at 10 08 01 AM" src="https://github.com/user-attachments/assets/73f44428-ffb5-41b8-a608-75480c431e23" />

**RESULT**
Thus, the implementation DES Encryption and Decryption are executed successfully.


