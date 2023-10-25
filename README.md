from cryptography.fernet import Fernet

# Generate a new AES key
key = Fernet.generate_key()
cipher_suite = Fernet(key)

# Word to encrypt
word_to_encrypt = "SecretWord"

# Encrypt the word
encrypted_word = cipher_suite.encrypt(word_to_encrypt.encode())

# Decrypt the word
decrypted_word = cipher_suite.decrypt(encrypted_word).decode()

print("Original Word:", word_to_encrypt)
print("Encrypted Word:", encrypted_word)
print("Decrypted Word:", decrypted_word)
