# Simple Python RAT (Remote Access Tool)

This project demonstrates a **Remote Access Tool (RAT)** built in Python, created for educational purposes to understand the basics of remote access and network security. It enables remote command execution, file downloading, and screen capturing functionalities between a victim (Windows) machine and an attacker (Kali Linux) machine.

> **Disclaimer:** This tool is intended strictly for educational and ethical learning. Unauthorized access to computer systems is illegal.

---

## 📜 Overview

- **Victim Side (Windows)**: Listens for incoming commands, executes them, captures screenshots, and transfers files.
- **Attacker Side (Kali Linux)**: Sends commands, downloads files, and receives screenshots from the victim.

Both machines must be on the same network unless additional network configurations (like port forwarding) are performed.

---

## 🔧 Prerequisites

- Python 3.x installed on both Windows and Kali Linux.
- Libraries:
  - `socket`
  - `subprocess`
  - `time`
  - `os`
  - `pyautogui`
- Additional Tools:
  - **PyInstaller** (for converting scripts to `.exe` for victim machine)
  - **WinRAR** (for creating self-extracting archive)

---

## 🚀 Setup and Execution

### Victim (Windows Machine)

1. Edit `victim.py` to include the attacker's IP address and port.
2. Convert the script into an executable:
   ```bash
   pyinstaller --onefile --noconsole victim.py
   ```
3. Create a self-extracting archive using WinRAR:
   - Add a decoy file and the executable.
   - Set the executable to auto-run after extraction.
   - Customize the icon for disguise (optional).

### Attacker (Kali Linux Machine)

1. Place the `attacker.py` script.
2. Update IP and port settings if necessary.
3. Run:
   ```bash
   python3 attacker.py
   ```

---

## 🛠️ Features

- **Remote Shell Access**: Execute system commands remotely.
- **File Downloading**: Download any file from the victim machine.
- **Screenshot Capture**: Remotely capture the victim’s screen.
- **Directory Navigation**: Change directories on the victim’s machine.

---

## 🌐 Extending Over Public Networks

You can extend functionality over public IPs by:
- Using your router's **port forwarding** settings.
- Replacing the private IP with your **public IP**.
- Configuring firewall and NAT rules carefully.

> **Note**: Due to ISP restrictions, router settings, or dynamic IPs, public deployment may not always work without additional setup like using a VPS or tunneling tools.

---

## 📚 References

- Sarwar, F. A. (2021). *Python Ethical Hacking From Scratch*. Packt Publishing Ltd.

---

## 🛡️ Legal Disclaimer

This project is meant **only** for educational demonstrations of security concepts. Unauthorized access, modification, or disruption of computer systems is illegal and punishable by law.

---
