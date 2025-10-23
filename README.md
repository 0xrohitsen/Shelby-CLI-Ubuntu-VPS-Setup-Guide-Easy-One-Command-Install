# 🚀 Shelby CLI — Ubuntu VPS Installation Guide

Shelby CLI lets you **upload, download, and manage files (blobs)** on the **Shelby Network**.  
This guide shows how to set up and use it easily on **Ubuntu or any Linux VPS**.


## 🧩 Prerequisites

Before installing Shelby CLI, make sure your system has Node.js and npm installed.

```bash
sudo apt update && sudo apt install -y nodejs npm git

> 🧠 Tip: Node.js version 18 or higher is recommended.



Check versions:

node -v
npm -v


---

⚙️ Step 1: Install Shelby CLI

Install Shelby CLI globally:

npm install -g @shelby-protocol/cli

Verify installation:

shelby --version


---

🏁 Step 2: Initialize Shelby CLI

Run the initialization command to set up configuration files:

shelby init

This will create a config file at:

~/.shelby/config.yaml

> 💡 During initialization, you can enter your API key (optional but recommended to avoid rate limits).



To view your config:

cat ~/.shelby/config.yaml


---

🌐 Step 3: Check Shelby Contexts

Verify that your Shelby networks (contexts) are configured correctly:

shelby context list

You should see both local and shelbynet networks listed.


---

👤 Step 4: Check Accounts

List available accounts:

shelby account list

Example output:

┌──────────────┬──────────────────────────────────────┬──────────────────┐
│ Name         │ Address                              │ Private Key      │
├──────────────┼──────────────────────────────────────┼──────────────────┤
│ alice        │ 0xfcb...a51c                         │ ed25519-priv-0x8 │
└──────────────┴──────────────────────────────────────┴──────────────────┘


---

💧 Step 5: Fund Your Account

You need APT tokens (for gas fees) and ShelbyUSD tokens (for uploads).

🔹 Get APT Tokens (Gas)

Use the Aptos faucet for shelbynet:

👉 https://faucet.shelbynet.shelby.xyz

🔹 Get ShelbyUSD Tokens

Use the Shelby faucet:

👉 https://explorer.shelby.xyz/faucet

Or via CLI (if supported):

shelby faucet fund --token ShelbyUSD --account alice


---

💰 Step 6: Check Account Balance

shelby account balance

Example output:

💰 Balance:
APT       9.99
ShelbyUSD 9.99


---

📤 Step 7: Upload a File

Upload any file to the Shelby network.

shelby upload /path/to/file.txt files/file.txt -e tomorrow --assume-yes

✅ Example output:

🚀 Upload complete — took 1.53s
🌐 Explorer: https://explorer.shelby.xyz/shelbynet/account/<ACCOUNT_ADDRESS>


---

📂 Step 8: Verify Uploaded Files

List all uploaded blobs:

shelby account blobs

Example:

📦  Stored Blobs
┌─────────────────────────────────────────────┬───────────────┬─────────────────────────┐
│ Name                                        │ Size          │ Expires                 │
├─────────────────────────────────────────────┼───────────────┼─────────────────────────┤
│ files/file.txt                              │ 494 B         │ Oct 11, 2025, 4:03 PM   │
└─────────────────────────────────────────────┴───────────────┴─────────────────────────┘


---

📥 Step 9: Download a File

Download any uploaded file from Shelby:

shelby download files/file.txt /path/to/save/file.txt


---

⚠️ Troubleshooting

❌ Error: Insufficient Shelby tokens

This means your account doesn’t have enough ShelbyUSD tokens.

Solution: Go to Shelby Faucet
and fund your account with ShelbyUSD.

You need both APT (gas) and ShelbyUSD (storage).


---

🧹 Optional Commands

List all Shelby CLI commands:

shelby --help

Uninstall Shelby CLI:

npm uninstall -g @shelby-protocol/cli


---

🧠 Summary (Quick Commands)

Task	Command

Install Shelby CLI	npm install -g @shelby-protocol/cli
Init CLI	shelby init
Check Contexts	shelby context list
Check Accounts	shelby account list
Check Balance	shelby account balance
Upload File	shelby upload file.txt files/file.txt -e tomorrow --assume-yes
Download File	shelby download files/file.txt /path/to/file.txt



---

🔗 Official Resources

🌐 Shelby Explorer: https://explorer.shelby.xyz

📘 Shelby Docs: https://docs.shelby.xyz

💧 Shelby Faucet: https://faucet.shelbynet.shelby.xyz



---

✨ Author

Made with ❤️ by @bigbrainless
Web3 Creator | Kaito Leaderboard | Shelby Network Contributor
