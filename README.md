# 🚀 Shelby CLI — Ubuntu VPS Installation Guide

Shelby CLI lets you upload, download, and manage files (blobs) on the Shelby Network.  
Follow these simple steps to install and use it easily on **Ubuntu** or **any Linux VPS**.

---

## 🧩 Prerequisites

Before installing, ensure **Node.js** and **npm** are installed.

```bash
sudo apt update && sudo apt install -y nodejs npm git
```

> 🧠 Tip: Node.js **v18+** is recommended.

Check versions:

```bash
node -v
```

```bash
npm -v
```

---

## ⚙️ Step 1: Install Shelby CLI

Install Shelby CLI globally:

```bash
npm install -g @shelby-protocol/cli
```

Verify installation:

```bash
shelby --version
```

---

## 🏁 Step 2: Initialize Shelby CLI

Initialize Shelby configuration:

```bash
shelby init
```

This creates your config file at:

```
~/.shelby/config.yaml
```

View the config file:

```bash
cat ~/.shelby/config.yaml
```

> 💡 During setup, you can enter your **API key** (optional but recommended).

---

## 🌐 Step 3: Check Shelby Contexts

List configured networks:

```bash
shelby context list
```

You should see both `local` and `shelbynet`.

---

## 👤 Step 4: Check Accounts

List available accounts:

```bash
shelby account list
```

Example:
```
┌──────────────┬──────────────────────────────────────┬──────────────────┐
│ Name         │ Address                              │ Private Key      │
├──────────────┼──────────────────────────────────────┼──────────────────┤
│ alice        │ 0xfcb...a51c                         │ ed25519-priv-0x8 │
└──────────────┴──────────────────────────────────────┴──────────────────┘
```

---

## 💧 Step 5: Fund Your Account

You’ll need both **APT tokens** (gas) and **ShelbyUSD tokens** (for uploads).

### 🔹 Get APT Tokens
👉 [https://faucet.shelbynet.shelby.xyz](https://faucet.shelbynet.shelby.xyz)

### 🔹 Get ShelbyUSD Tokens
👉 [https://explorer.shelby.xyz/faucet](https://explorer.shelby.xyz/faucet)

Or fund via CLI:

```bash
shelby faucet fund --token ShelbyUSD --account alice
```

---

## 💰 Step 6: Check Account Balance

```bash
shelby account balance
```

Example:
```
💰 Balance:
APT       9.99
ShelbyUSD 9.99
```

---

## 📤 Step 7: Upload a File

Upload any file:

```bash
shelby upload /path/to/file.txt files/file.txt -e tomorrow --assume-yes
```

✅ Example output:
```
🚀 Upload complete — took 1.53s
🌐 Explorer: https://explorer.shelby.xyz/shelbynet/account/<ACCOUNT_ADDRESS>
```

---

## 📂 Step 8: Verify Uploaded Files

```bash
shelby account blobs
```

Example:
```
📦 Stored Blobs
┌─────────────────────────────────────────────┬───────────────┬─────────────────────────┐
│ Name                                        │ Size          │ Expires                 │
├─────────────────────────────────────────────┼───────────────┼─────────────────────────┤
│ files/file.txt                              │ 494 B         │ Oct 11, 2025, 4:03 PM   │
└─────────────────────────────────────────────┴───────────────┴─────────────────────────┘
```

---

## 📥 Step 9: Download a File

```bash
shelby download files/file.txt /path/to/save/file.txt
```

---

## ⚠️ Troubleshooting

### ❌ Error: Insufficient Shelby Tokens
This means your account doesn’t have enough **ShelbyUSD**.

✅ Fix:
- Visit the [Shelby Faucet](https://explorer.shelby.xyz/faucet)
- Fund your account with both **APT (gas)** and **ShelbyUSD (storage)**

---

## 🧹 Optional Commands

List all commands:

```bash
shelby --help
```

Uninstall Shelby CLI:

```bash
npm uninstall -g @shelby-protocol/cli
```

---

## 🧠 Quick Summary

| Task | Command |
|------|----------|
| Install CLI | `npm install -g @shelby-protocol/cli` |
| Init CLI | `shelby init` |
| Check Contexts | `shelby context list` |
| Check Accounts | `shelby account list` |
| Check Balance | `shelby account balance` |
| Upload File | `shelby upload file.txt files/file.txt -e tomorrow --assume-yes` |
| Download File | `shelby download files/file.txt /path/to/file.txt` |

---

## 🔗 Official Links

🌐 [Shelby Explorer](https://explorer.shelby.xyz)  
📘 [Shelby Docs](https://docs.shelby.xyz)  
💧 [Shelby Faucet](https://faucet.shelbynet.shelby.xyz)

---

## ✨ Author

Made with ❤️ by [@bigbrainless](https://x.com/bigbrainless)  
Web3 Creator | Kaito Leaderboard | Shelby Network Contributor
