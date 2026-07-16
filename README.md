# Arcanux

<p align="center">
  <strong>Post-Quantum Secure Data Hiding Platform</strong><br>
  A cross-platform application that combines post-quantum cryptography and steganography to securely encrypt and conceal sensitive information inside multimedia files.
</p>

---

## Table of Contents

- Overview
- Features
- Architecture
- Cryptographic Workflow
- Threat Model
- Technology Stack
- Project Structure
- Installation
- Usage
- Security Design
- Current Limitations
- Roadmap
- Testing
- Contributing
- License

---


## Overview

Arcanux is a desktop application developed to provide an additional layer of security beyond traditional encryption by combining **post-quantum cryptography** with **digital steganography**.

Instead of only encrypting confidential data, Arcanux encrypts the information using quantum-resistant algorithms and embeds the encrypted ciphertext inside carrier media such as images. Even if an attacker gains access to the carrier file, recovering the original information remains computationally infeasible without the appropriate private key.

The project focuses on confidentiality, secure data transmission, usability, and future-proof cryptographic protection.

---

## Key Features

- Post-Quantum Cryptography integration
- Encrypt-then-Embed architecture
- Image Steganography
- Cross-platform graphical interface
- Automatic encryption and embedding workflow
- Secure extraction and decryption
- Multiple file type support
- File integrity validation
- Error handling and recovery mechanisms
- Simple user-friendly interface

---

## Why Arcanux?

Traditional encrypted files are obvious targets.

Arcanux reduces exposure by hiding encrypted information inside ordinary media files, making sensitive data significantly less conspicuous while maintaining cryptographic protection.

This layered approach provides:

- Confidentiality
- Obfuscation
- Future-resistant encryption
- Secure storage
- Secure file sharing

---


# Architecture 

    Secret File
      │
      ▼
    ML-KEM-768
      │
      ▼
    Shared Secret
      │
      ▼  
    HKDF
      │
      ▼
    ChaCha20-Poly1305
      │
      ▼
    Encrypted Container
      │
      ▼
    LSB Steganography
      │
      ▼
    Carrier Image
      │
      ▼
    Extraction
      │
      ▼
    ChaCha20-Poly1305
      │
      ▼
    Recovered File

---

# Threat Model

Designed to protect against:

- Unauthorized access to confidential files
- Passive interception of transmitted media
- Casual inspection of carrier images

Not designed to protect against:

- Compromised host systems
- Advanced forensic steganalysis
- Side-channel attacks
- Private key compromise

---

# Technology Stack

| Component | Technology |
|-----------|------------|
| Language | Python 3.12+ |
| GUI | PySide6 |
| PQC | ML-KEM-768 (Kyber) |
| AEAD | ChaCha20-Poly1305 |
| KDF | HKDF |
| Steganography | Least Significant Bit (LSB) |
| Image Processing | Pillow |
| Packaging | PyInstaller |

---

# Project Structure

```text
Arcanux/
├── README.md
├── LICENSE
├── requirements.txt
├── .gitignore
├── docs/
├── assets/
│   └── screenshots/
├── src/
│   ├── crypto/
│   ├── gui/
│   ├── steganography/
│   ├── utils/
│   └── main.py
└── tests/
```

---

# Usage

1. Launch Arcanux.
2. Select a carrier image.
3. Select the file to protect.
4. Generate or load keys.
5. Encrypt the payload.
6. Embed the encrypted container.
7. Save the generated image.

To recover data:

1. Open the carrier image.
2. Extract the embedded container.
3. Decrypt using the required key.
4. Recover the original file.

---

# Security Design

Arcanux follows an **Encrypt-then-Embed** workflow.

- ML-KEM-768 establishes a shared secret.
- HKDF derives the symmetric encryption key.
- ChaCha20-Poly1305 encrypts and authenticates the payload.
- LSB steganography conceals the encrypted container within the carrier image.

This separation ensures confidentiality and integrity before steganographic embedding.

---

# Testing

Planned testing includes:

- Encryption/decryption correctness
- Round-trip embedding and extraction
- Invalid input handling
- Corrupted carrier detection
- GUI workflow validation

Performance metrics and benchmarks will be published once implemented.

---

# Current Limitations

- Image steganography only (PNG/BMP)
- No audio support in MVP
- No digital signatures
- No cloud synchronization
- Educational/research implementation

---

# Roadmap

- [ ] WAV audio support
- [ ] Randomized embedding
- [ ] Drag-and-drop UI
- [ ] Batch processing
- [ ] Additional PQC algorithms
- [ ] Comprehensive benchmark suite

---

# Contributing

Contributions, bug reports, and suggestions are welcome. Please open an issue before proposing major architectural changes.

---

# Author

**Dipesh**

Cybersecurity • Security Engineering • Applied Cryptography • Security Analyst

GitHub: https://github.com/11xNecronaut

LinkedIn: https://www.linkedin.com/in/dipesh-74549234b/

---

# Acknowledgements

This project explores the practical integration of post-quantum cryptography and steganography in a desktop application while emphasizing sound engineering practices, transparent threat modeling, and maintainable software design.







