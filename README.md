# IP Address Puller

A lightweight, automated Bash script designed to capture network traffic and extract IP addresses using the power of **Wireshark** (via its command-line counterpart, `tshark`). 

This tool is ideal for network administrators, security enthusiasts, or anyone looking to analyze live network traffic and pull source/destination IP addresses on the fly.

---

## 🚀 Features

* **Live Traffic Capture:** Sniffs network packets in real-time from a specified interface.
* **Automatic IP Extraction:** Filters and extracts unique source and destination IP addresses.
* **Packet Filtering:** Automatically filters out common noise or targets specific protocols.
* **Clean Output:** Displays results cleanly in the terminal or logs them to a text file for further analysis.

---

## 📋 Prerequisites

Before running the script, ensure you have the necessary dependencies installed:

### 1. Install Wireshark / Tshark
The script relies on `tshark` (Wireshark's CLI tool) to capture and parse packets.

* **Debian/Ubuntu:**
    ```bash
    sudo apt update && sudo apt install tshark -y
    ```
* **Arch Linux:**
    ```bash
    sudo pacman -S wireshark-cli
    ```
* **macOS (via Homebrew):**
    ```bash
    brew install wireshark
    ```

### 2. Permissions (Crucial)
Capturing network packets usually requires root privileges. You can either run the script with `sudo` or configure Wireshark to run without root:
```bash
sudo dpkg-reconfigure wireshark-common
sudo usermod -aG wireshark $USER
