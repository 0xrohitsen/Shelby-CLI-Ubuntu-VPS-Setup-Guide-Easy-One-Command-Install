That's an excellent, well-structured guide! The request for separate copy buttons for every command is a great idea for a GitHub README because it significantly improves the user experience.
I'll take your optimized content and transform it into a clean, modern, and highly user-friendly GitHub README, complete with the requested structure and a clear, distinct copy button for every single command.
Since I cannot generate the actual GitHub "copy" functionality (which is a feature of the GitHub UI itself), I will use GitHub-flavored Markdown (GFM) code blocks and bold keywords to make the commands stand out and be instantly copyable. I'll also use consistent formatting, clear headings, and emojis to make it highly engaging and easy to follow.
Here is the ready-to-upload Markdown file (README.md):
# 🚀 Shelby CLI — Ubuntu VPS Installation Guide

Shelby CLI is your command-line interface for seamless file management on the **Shelby Network**. Use it to upload, download, and manage your files (blobs) directly from your terminal.

This comprehensive guide shows you how to easily set up and use the Shelby CLI on **Ubuntu** or any standard Linux VPS.

---

## 🧩 Prerequisites

Before installing the Shelby CLI, ensure your system has **Node.js** and **npm** installed, along with **git**.

### Install Prerequisites

Run the following command to update your packages and install the necessary tools:

```bash
sudo apt update && sudo apt install -y nodejs npm git

> 🧠 Tip: Node.js version 18 or higher is recommended for the best experience.
> 
Verify Installation
Check the versions to confirm everything is set up correctly:
node -v

npm -v

⚙️ Installation and Setup
Step 1: Install Shelby CLI
Install the Shelby CLI package globally using npm:
npm install -g @shelby-protocol/cli

Verify Shelby CLI
Confirm the installation by checking the version:
shelby --version

Step 2: Initialize Shelby CLI
Run the initialization command to set up the default configuration files:
shelby init

This command creates the primary configuration file:
~/.shelby/config.yaml
> 💡 API Key: During initialization, you'll be prompted for an API key. This is optional but highly recommended to avoid rate limits.
> 
View Configuration
You can view the contents of your new config file at any time:
cat ~/.shelby/config.yaml

🌐 Network and Account Checks
Step 3: Check Shelby Contexts (Networks)
Verify that the available networks (contexts) are listed correctly:
shelby context list

You should see both the local and shelbynet networks in the output.
Step 4: Check Accounts
List all available accounts. This is where your wallet address is stored:
shelby account list

Example Output:
| Name | Address | Private Key |
|---|---|---|
| alice | 0xfcb...a51c | ed25519-priv-0x8 |
💰 Funding Your Account
You need two types of tokens to use the Shelby Network:
 * APT (gas for transaction fees).
 * ShelbyUSD (for storage/upload costs).
Step 5: Fund Your Account
A. Get APT Tokens (Gas):
Use the official faucet to fund your account:
👉 https://faucet.shelbynet.shelby.xyz
B. Get ShelbyUSD Tokens (Storage):
Fund your account using the explorer's faucet or the CLI command below:
👉 https://explorer.shelby.xyz/faucet
Alternatively, use the CLI:
shelby faucet fund --token ShelbyUSD --account alice

Step 6: Check Account Balance
Always check your balance before attempting uploads:
shelby account balance

Example Output: 💰 Balance: APT 9.99 ShelbyUSD 9.99
📤 File Management
Step 7: Upload a File
Use the shelby upload command to put a file onto the Shelby Network.
 * Replace /path/to/file.txt with your local file path.
 * files/file.txt is the name the file will have on the network.
 * -e tomorrow sets an expiration date.
 * --assume-yes skips the confirmation prompt.
<!-- end list -->
shelby upload /path/to/file.txt files/file.txt -e tomorrow --assume-yes

Example Output:
🚀 Upload complete — took 1.53s
🌐 Explorer: https://explorer.shelby.xyz/shelbynet/account/<ACCOUNT_ADDRESS>
Step 8: Verify Uploaded Files
List all files (blobs) currently stored on your account:
shelby account blobs

Example Output:
| Name | Size | Expires |
|---|---|---|
| files/file.txt | 494 B | Oct 11, 2025, 4:03 PM |
Step 9: Download a File
Use the shelby download command to retrieve a file:
 * files/file.txt is the name of the file on the network.
 * /path/to/save/file.txt is where you want the file saved locally.
<!-- end list -->
shelby download files/file.txt /path/to/save/file.txt

⚠️ Troubleshooting
| Error | Solution |
|---|---|
| ❌ Error: Insufficient Shelby tokens | You need more ShelbyUSD tokens for storage and APT tokens for gas. |
|  | ✅ Solution: Go to the Shelby Faucet and fund your account with both ShelbyUSD and APT. |
🧹 Optional Commands
List All Commands
Get a full list of all available Shelby CLI commands:
shelby --help

Uninstall Shelby CLI
If you need to remove the CLI:
npm uninstall -g @shelby-protocol/cli

🧠 Summary (Quick Command Reference)
| Task | Command |
|---|---|
| Install CLI | npm install -g @shelby-protocol/cli |
| Init CLI | shelby init |
| Check Contexts | shelby context list |
| Check Accounts | shelby account list |
| Check Balance | shelby account balance |
| Upload File | shelby upload file.txt files/file.txt -e tomorrow --assume-yes |
| Download File | shelby download files/file.txt /path/to/file.txt |
🔗 Official Resources
| Resource | Link |
|---|---|
| 🌐 Shelby Explorer | https://explorer.shelby.xyz |
| 📘 Shelby Docs | https://docs.shelby.xyz |
| 💧 Shelby Faucet | https://explorer.shelby.xyz/faucet |
✨ Author
Made with ❤️ by @bigbrainless
Web3 Creator | Kaito Leaderboard | Shelby Network Contributor

