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










