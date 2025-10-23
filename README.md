Perfect 🔥

Here’s your fully optimized GitHub-ready README.md, rewritten for clean structure, clarity, and separate copy buttons for every command — so users can copy each step individually right from GitHub.


---

🚀 Shelby CLI — Ubuntu VPS Installation Guide

Shelby CLI lets you upload, download, and manage files (blobs) on the Shelby Network.
This guide shows how to set up and use it easily on Ubuntu or any Linux VPS.


---

🧩 Prerequisites

Before installing Shelby CLI, make sure your system has Node.js and npm installed.

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

Run initialization to set up configuration files:

shelby init

This will create:

~/.shelby/config.yaml

> 💡 During initialization, enter your API key (optional but recommended to avoid rate limits).



View your config:

cat ~/.shelby/config.yaml


---

🌐 Step 3: Check Shelby Contexts

Verify networks (contexts):

shelby context list

You should see both local and shelbynet networks.


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

You need APT tokens (gas) and ShelbyUSD tokens (for uploads).

🔹 Get APT Tokens (Gas):
👉 https://faucet.shelbynet.shelby.xyz

🔹 Get ShelbyUSD Tokens:
👉 https://explorer.shelby.xyz/faucet

Or via CLI:

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

Upload any file to Shelby:

shelby upload /path/to/file.txt files/file.txt -e tomorrow --assume-yes

✅ Example output:

🚀 Upload complete — took 1.53s
🌐 Explorer: https://explorer.shelby.xyz/shelbynet/account/<ACCOUNT_ADDRESS>


---

📂 Step 8: Verify Uploaded Files

shelby account blobs

Example:

📦 Stored Blobs
┌─────────────────────────────────────────────┬───────────────┬─────────────────────────┐
│ Name                                        │ Size          │ Expires                 │
├─────────────────────────────────────────────┼───────────────┼─────────────────────────┤
│ files/file.txt                              │ 494 B         │ Oct 11, 2025, 4:03 PM   │
└─────────────────────────────────────────────┴───────────────┴─────────────────────────┘


---

📥 Step 9: Download a File

shelby download files/file.txt /path/to/save/file.txt


---

⚠️ Troubleshooting

❌ Error: Insufficient Shelby tokens

This means your account doesn’t have enough ShelbyUSD tokens.

✅ Solution:
Go to Shelby Faucet and fund your account with ShelbyUSD.
You need both APT (gas) and ShelbyUSD (storage).


---

🧹 Optional Commands

List all CLI commands:

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

🌐 Shelby Explorer
📘 Shelby Docs
💧 Shelby Faucet


---

✨ Author

Made with ❤️ by @bigbrainless
Web3 Creator | Kaito Leaderboard | Shelby Network Contributor


---

Would you like me to generate a ready-to-upload Markdown file (README.md) for this version so you can directly replace it on GitHub?
