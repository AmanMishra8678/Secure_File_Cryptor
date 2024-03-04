# Secure_File_Cryptor
Encrypt and decrypt your files and folders using password.
# File Encryption and Decryption Script

This Python script provides a simple yet powerful file encryption and decryption utility using the Fernet symmetric encryption algorithm. It allows you to secure individual files or entire folders with a password.

## Features

- **Password-Based Encryption:** Uses a user-provided password to derive an encryption key.
- **Salt Generation:** Generates a salt for key derivation and securely stores it.
- **File Encryption:** Encrypts individual files using Fernet encryption.
- **Folder Encryption:** Recursively encrypts all files within a specified folder.
- **File Decryption:** Decrypts encrypted files back to their original state.
- **Folder Decryption:** Recursively decrypts all files within a specified folder.

## Usage

### Requirements

- Python 3.x
- Required Python packages: `cryptography`

### Command-Line Usage

```bash
python script_name.py <path> [-s <salt_size>] [-e | -d]
```

- `<path>`: Path to the file or folder you want to encrypt/decrypt.
- `-s, --salt-size <salt_size>`: (Optional) Size of the salt used for key derivation. If not provided, it loads an existing salt.
- `-e, --encrypt`: (Optional) Specify to encrypt the file or folder.
- `-d, --decrypt`: (Optional) Specify to decrypt the file or folder.

### Examples

#### Encrypt a File

```bash
python ransomware.py -e path/to/file.txt -s 32
```

#### Encrypt a Folder

```bash
python ransomware.py -e path/to/folder -s 32
```

#### Decrypt a File

```bash
python ransomware.py -d path/to/encrypted_file.txt
```

#### Decrypt a Folder

```bash
python ransomware.py -d path/to/encrypted_folder 
```

## Security Note

- **Salt Storage:** The script securely stores the salt used for key derivation in a file named `salt.salt` in the same directory as the script. Ensure this file is kept confidential.

## Warning

- **Invalid Password Handling:** If an incorrect password is provided during decryption, the script will detect it and print an error message.

## Dependencies

- [cryptography](https://cryptography.io/): A Python library that provides cryptographic recipes and primitives.
