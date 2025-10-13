# 💣 Ransomware Simulation Project  
**Language:** Go (Golang) | **Platform:** Windows (Simulated on VMware) | **Contributions:** Welcome! 

---

## 📋 Table of Contents
- [Overview](#-overview)
- [Key Features](#-key-features)
- [System Architecture](#-system-architecture)
- [Technical Implementation](#-technical-implementation)
- [Installation](#-installation)
- [Usage](#-usage)
- [Demonstration Flow](#-demonstration-flow)
- [Ethical & Security Considerations](#-ethical--security-considerations)
- [Challenges & Learnings](#-challenges--learnings)
- [Contributing](#-contributing)
- [License](#-license)

---

## 🔍 Overview
The **Ransomware Simulation Project** is a controlled cybersecurity mini-project designed to **demonstrate how ransomware attacks function** in a safe and ethical environment.  

It simulates the **entire ransomware lifecycle**, from infection to encryption, ransom note generation, and eventual file decryption upon payment (for demonstration only).  

The simulation serves educational and research purposes — helping cybersecurity students, researchers, and analysts better understand ransomware behavior and defensive mechanisms.

### 🎯 Objective
To simulate a **real-world ransomware attack scenario** using Golang, demonstrating:
- AES-256 file encryption & decryption.
- Creation of ransom notes with unique victim IDs.
- Controlled decryption process after simulated ransom “payment”.
- Windows-focused payload execution and recovery.

---

## 🚀 Key Features

### 🔐 Core Capabilities
- **AES-256 Bit Encryption** – Secure and fast encryption of victim files.  
- **Automated File Scanning** – Recursively encrypts all user directories.  
- **Unique Victim Identifier** – Each victim system receives a personalized ID.  
- **Ransom Note Generation** – Creates `README.txt` in each encrypted directory with ransom instructions.

### 🧩 Decryption & Recovery
- **Custom Decryptor Executable** – Developed in Golang to reverse the encryption.  
- **Ransom Note Cleanup** – Automatically deletes ransom notes after successful decryption.

### 💻 Platform & Execution
- **Developed on:** Kali Linux  
- **Target Environment:** Windows (tested on VMware)  
- **Executable Format:** `.exe` files generated using cross-compilation in Go  

---

## 🏗 System Architecture
    ┌────────────────────────┐
    │   Victim Downloads     │
    │  Fake Spotify Premium  │
    └───────────┬────────────┘
                │
                ▼
    ┌────────────────────────┐
    │   Encryptor Executed    │
    │  → Encrypts Files (AES) │
    │  → Creates README.txt   │
    └───────────┬────────────┘
                │
                ▼
    ┌────────────────────────┐
    │ Victim Contacts Attacker│
    │  (Email + ID)           │
    └───────────┬────────────┘
                │
                ▼
    ┌────────────────────────┐
    │   Decryptor Provided    │
    │  → Uses Decryption Key  │
    │  → Restores Files       │
    │  → Removes Ransom Notes │
    └────────────────────────┘


---

## ⚙️ Technical Implementation

- **Language:** Go (Golang)  
- **Encryption Algorithm:** AES-256-CBC  
- **Key & IV Handling:** Generated dynamically during encryption  
- **File Targeting:** Recursive directory traversal  
- **Output Files:**  
  - Encrypted files (same name, encrypted content)  
  - Ransom note (`README.txt`) with contact email and victim ID  

---

## 💻 Installation

### 🧰 Prerequisites
- Go 1.18+  
- VMware or VirtualBox (for sandbox testing)  
- Windows OS environment (for executable execution)

### 📦 Steps
```bash
# Clone the repository
git clone https://github.com/mnfibin/ransomware_simulation.git
cd ransomware_simulation

# (Optional,for Linux or macOS) Compile Encryptor
GOOS=windows GOARCH=amd64 go build encryptor.go

# (Optional,for Linux or macOS) Compile Decryptor
GOOS=windows GOARCH=amd64 go build decryptor.go

