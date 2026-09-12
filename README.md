# 🌐 FreeNET

A lightweight, independent, and open-source network gateway built with a focus on **simplicity, freedom, and portability**.

No heavy panels.  
No databases.  
No unnecessary complexity.

Just a clean, containerized routing engine designed to run anywhere. 🚀

**[🇮🇷 فارسی](README-fa.md)**

[![Python](https://img.shields.io/badge/Python-3.10+-blue.svg)](https://www.python.org/)
[![Docker](https://img.shields.io/badge/Docker-Ready-2496ED.svg)](https://www.docker.com/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

---

# ⚡ Quick Start

Get FreeNET running in a few simple steps.

## 1. Clone the repository

```bash
git clone https://github.com/MHDLabs/FreeNET.git
cd FreeNET
````

## 2. Configure environment variables

Create a `.env` file:

```env
SUBSCRIPTION_TOKEN=your_secure_token_here
PORT=8080
```

`SUBSCRIPTION_TOKEN` is required and must be manually configured.

## 3. Build and run with Docker

```bash
docker build -t freenet .

docker run -d \
  --name freenet \
  --env-file .env \
  -p 8080:8080 \
  freenet
```

That's it. FreeNET is ready. ✨

---

# 🎯 What is FreeNET?

FreeNET was created with a simple idea:

**Network tools should not become complicated just because they become powerful.**

Many existing solutions rely on large dashboards, databases, user management systems, and unnecessary layers.

FreeNET takes another approach.

It is a lightweight FastAPI-based network gateway designed to be:

* Simple to understand
* Easy to deploy
* Portable across platforms
* Friendly with Docker environments

No vendor lock-in.
No unnecessary layers.
Just your infrastructure, your way. 🌍

---

# ✨ Features

* ⚡ **Lightweight**

  * Minimal resource usage
  * Built with FastAPI

* 🐳 **Docker First**

  * Designed from the beginning for container environments

* 🔌 **Multiple Protocol Support**

  * VLESS WebSocket
  * Trojan WebSocket
  * VLESS XHTTP packet-up

* 📦 **Simple Subscription System**

  * Standard Base64 subscription output
  * Compatible with common clients

* 📊 **Built-in Statistics**

  * Server uptime tracking
  * Upload and download traffic statistics

* 🔐 **Environment Based Configuration**

  * No complicated configuration files

* 🧩 **Minimal Architecture**

  * No external database dependency
  * Small and readable codebase

---

# 📡 Supported Protocols

## VLESS WebSocket

A lightweight and widely supported transport method.

## Trojan WebSocket

Password-based authenticated routing with secure password hashing.

## VLESS XHTTP

Modern XHTTP transport support using packet-up mode for flexible network environments.

---

# 🏗️ Project Structure

FreeNET intentionally keeps its architecture simple, flat, and readable:

```text
FreeNET/
├── main.py                 # FastAPI application, routing and subscription system
├── core.py                 # Core utilities, relay logic and statistics
├── protocols/
│   ├── vless.py            # VLESS handler
│   ├── trojan.py           # Trojan handler
│   └── xhttp.py            # XHTTP handler
├── Dockerfile              # Container configuration
└── requirements.txt        # Python dependencies
```

---

# ⚙️ Configuration

FreeNET is configured entirely through environment variables.

| Variable             | Required | Description                              |
| -------------------- | -------- | ---------------------------------------- |
| `SUBSCRIPTION_TOKEN` | ✅ Yes    | Access token for `/sub/{token}` endpoint |
| `VLESS_UUID`         | ❌ No     | Custom UUID for VLESS/XHTTP              |
| `TROJAN_PASSWORD`    | ❌ No     | Custom password for Trojan               |
| `PORT`               | ❌ No     | Server listening port (default: `8080`)  |

If `VLESS_UUID` or `TROJAN_PASSWORD` are not provided, FreeNET can generate them automatically.

The subscription token is always controlled by the user and must be configured manually.

---

# 🚀 Deployment

FreeNET is platform-independent.

You can deploy it on:

* 🖥️ Personal servers
* ☁️ Cloud platforms
* 🐳 Any Docker-compatible environment
* 🏠 Home servers

The goal is simple:

**If Docker runs, FreeNET runs.**

No dependency on a specific provider.
No vendor lock-in.

---

# 📋 Subscription System

The endpoint:

```text
https://your-domain/sub/YOUR_TOKEN
```

returns a Base64 encoded subscription compatible with:

* v2rayNG
* NekoBox
* Shadowrocket
* Other compatible clients

The subscription contains:

1. Active connection configurations
2. Supported protocol profiles
3. Server status information including uptime and traffic statistics

This is a configuration delivery system, not a user management panel.

---

# 🧠 Philosophy

## Why FreeNET?

Because bigger is not always better.

```text
Simple > Complex

Freedom > Lock-in

Portable > Platform dependent

Readable > Over-engineered
```

FreeNET is not trying to become another huge management panel.

It is a small tool built around one idea:

**Your infrastructure should stay under your control.**

---

# 🌍 Community

Follow the project, report issues, or contribute:

* GitHub:
  [https://github.com/MHDLabs/FreeNET](https://github.com/MHDLabs/FreeNET)

* Telegram:
  [https://t.me/MHDLabs](https://t.me/MHDLabs)

---

# ❤️ About

Made with ❤️ for the people of Iran and everyone around the world who experience the challenges of restricted internet access.

Made by MHDLabs

---

# 📜 License

This project is licensed under the MIT License.
