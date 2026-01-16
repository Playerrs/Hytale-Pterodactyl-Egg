
> This project has been DISCONTINUED because a better and more well-made version exists by NATroutter. Follow the link.
> https://github.com/NATroutter/egg-hytale/tree/main

---

# 🧊 Hytale Dedicated Server – Pterodactyl Setup

This repository provides an automated and secure setup for running a **Hytale Dedicated Server** inside the **Pterodactyl Panel**, including authentication, downloading, and startup management.

The system is designed to be **user-friendly**, **secure**, and **fully automated**, while still allowing full control through configuration files.

---

## ✨ Features

* ✅ Fully automated server download & installation
* 🔐 Secure OAuth Device Authentication (no passwords stored)
* 🧠 Intelligent first-run detection
* 🔁 Persistent login credentials
* ⚙️ Centralized Hytale server configuration
* 📦 Clean install and automatic cleanup
* 🧩 Designed specifically for Pterodactyl environments

---

## 🚀 How It Works (High-Level Overview)

### 1️⃣ First Installation

When the server is installed for the first time:

* Required dependencies are installed automatically
* The official **Hytale Downloader** is downloaded
* A startup script and configuration files are created
* The server is prepared but **not started yet**

---

### 2️⃣ First Startup (Authentication Required 2X)

On the first startup:

* A **login URL** will appear in the console
* Open the link, sign in with your Hytale account, and approve access
* Authentication tokens are securely stored
* The server files are downloaded and extracted automatically

⚠️ **Do not stop the server during this step**

---

### 3️⃣ Normal Startup

On subsequent starts:

* Authentication is skipped automatically
* Existing server files are detected
* The server starts immediately using saved credentials

**No additional action is required.**

---

## ⚙️ Configuration

### `hytale-settings.txt`

This file contains **only Hytale server arguments**.

It is read on every server start and controls:

* Network bind address and port
* Asset paths
* Server-specific runtime flags
* Gameplay or environment options supported by Hytale

📌 **Important:**

* This file **does NOT control Java or JVM options**
* Java memory, GC, and performance flags must be configured via:

  * Directly in the `start.sh` Java invocation

A reminder message is displayed on every startup indicating that this file controls **Hytale flags only**.

---

## 🔐 Security Model

* OAuth Device Flow is used (no email/password input)
* Tokens are stored locally with restricted permissions
* Credentials persist across restarts
* No sensitive data is printed or logged unnecessarily

---

## 📁 Directory Structure (Simplified)

```
/
├─ Server/                  # Hytale server files
├─ Assets.zip/              # Hytale Assets file
├─ start.sh                 # Startup entrypoint
├─ hytale-settings.txt      # Hytale server arguments
├─ .hytale-user.conf        # Profile configuration (protected)
├─ .hytale-downloader-credentials.json
```

---

## 🧠 Smart Behavior

* Automatically detects if the server is already installed
* Automatically downloads missing files
* Automatically cleans up temporary data
* Safe to restart
* Fully compatible with automation and modded environments

---

## 🛠 Requirements

* Pterodactyl Panel (Debian-based recommended)
* A valid Hytale account

---

## 🧪 Tested Environment

* Pterodactyl Panel
* Docker-based containers
* Debian / Ubuntu images

---

## ❗ Important Notes

* This setup is intended for **legitimate Hytale accounts only**
* The server cannot start without proper authentication
* Reloading the Pterodactyl console during authentication may interrupt the process
* Always edit configuration through `hytale-settings.txt`

---

## ❤️ Credits

* Hytale by Hypixel Studios
* Official Hytale Downloader

---

## 📌 Disclaimer

This project is **not affiliated with or endorsed by Hypixel Studios or Pterodactyl Panel**.
All trademarks belong to their respective owners.

---

