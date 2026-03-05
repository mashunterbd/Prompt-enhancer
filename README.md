# ✦ Prompt Enhancer Pro

<div align="center">

![Prompt Enhancer Pro](https://img.shields.io/badge/Version-4.0.0-4f8cff?style=for-the-badge&logo=googlechrome&logoColor=white)
![Manifest V3](https://img.shields.io/badge/Manifest-V3-9d5cfc?style=for-the-badge)
![License](https://img.shields.io/badge/License-MIT-3dd68c?style=for-the-badge)
![Platform](https://img.shields.io/badge/Platform-Chrome%20%7C%20Edge-f59e0b?style=for-the-badge)

**A powerful Chrome Extension that lets you automate any text transformation with a simple right-click — powered by your own AI backend via n8n webhooks.**

[⬇️ **Download v4.0.0**](https://github.com/mashunterbd/Prompt-enhancer/releases/tag/4.0.0) | [🐛 Report Bug](https://github.com/mashunterbd/Prompt-enhancer/issues) | [💡 Request Feature](https://github.com/mashunterbd/Prompt-enhancer/issues)

</div>

---

## 📋 Table of Contents

- [Overview](#-overview)
- [Features](#-features)
- [How It Works](#-how-it-works)
- [Installation](#-installation)
- [Setup & Configuration](#-setup--configuration)
- [Adding Automation Actions](#-adding-automation-actions)
- [Webhook Configuration (n8n)](#-webhook-configuration-n8n)
- [Security & Password](#-security--password)
- [Usage Guide](#-usage-guide)
- [Future Features](#-future-features)
- [FAQ](#-faq)

---

## 🌟 Overview

**Prompt Enhancer Pro** is a Chrome Extension that connects your browser to any AI automation backend. Select any text on any webpage, right-click, and instantly trigger powerful AI-powered transformations — text enhancement, translation, grammar fixing, summarization, or any custom workflow you build.

The extension uses **n8n** (open-source workflow automation) as the backend engine, giving you unlimited flexibility to design exactly the AI behavior you want.

```
Select Text  →  Right-Click  →  Choose Action  →  Text Auto-Replaced ✓
```

---

## ✨ Features

### Core Features
| Feature | Description |
|---|---|
| 🖱️ **Right-Click Context Menu** | Select text anywhere → right-click → choose your action |
| ⚡ **Instant Text Replacement** | Original selected text is automatically replaced with AI output |
| 🔧 **Up to 8 Custom Actions** | Create up to 8 different automation actions, each with its own webhook |
| 🔒 **Webhook Security** | Webhook URLs are password-protected and hidden from the UI |
| 👁️ **Live Menu Preview** | See exactly how your right-click menu will look inside the popup |
| 🟢 **Active/Inactive Status** | Enable or disable any action without deleting it |
| 🌐 **Works Everywhere** | Compatible with all websites — Facebook, Gmail, Google Docs, Notepad, etc. |
| 🎨 **Shadow DOM Toasts** | Clean, non-intrusive notification system that never conflicts with page styles |

### Automation Capabilities (via n8n)
| Capability | Example Use Case |
|---|---|
| ✍️ **Text Enhancement** | Improve clarity, tone, and professionalism of Bengali or English text |
| 🌍 **Translation** | Translate Bengali → English or any language pair |
| 📝 **Grammar Fixing** | Auto-correct spelling and grammar mistakes |
| 📄 **Summarization** | Condense long paragraphs into short summaries |
| 🎯 **SEO Optimization** | Transform raw content into SEO-friendly text |
| 🗞️ **News Title Generation** | Generate engaging headlines from story text |
| 🤖 **Any Custom AI Task** | If n8n can do it, this extension can trigger it |

---

## 🔄 How It Works

```
┌─────────────────────────────────────────────────────────┐
│                    BROWSER (Your PC)                    │
│                                                         │
│  1. You select text on any webpage                      │
│  2. You right-click → choose an action                  │
│  3. Extension captures the selected text                │
│                          │                              │
└──────────────────────────┼──────────────────────────────┘
                           │ POST { "text": "..." }
                           ▼
┌─────────────────────────────────────────────────────────┐
│                  n8n Webhook Server                     │
│                                                         │
│  4. Webhook receives the text                           │
│  5. AI Agent processes it (GPT-4, Claude, etc.)        │
│  6. Returns enhanced/transformed text                   │
│                          │                              │
└──────────────────────────┼──────────────────────────────┘
                           │ [{ "enhanced": "..." }]
                           ▼
┌─────────────────────────────────────────────────────────┐
│                    BROWSER (Your PC)                    │
│                                                         │
│  7. Extension receives the AI response                  │
│  8. Original selected text is REPLACED automatically    │
│  9. Toast notification: "✓ Done!"                       │
│                                                         │
└─────────────────────────────────────────────────────────┘
```

---

## 📥 Installation

### Step 1 — Download the Extension

<div align="center">

### [⬇️ Click Here to Download Prompt Enhancer Pro v4.0.0](https://github.com/mashunterbd/Prompt-enhancer/releases/tag/4.0.0)

</div>

### Step 2 — Extract the ZIP

1. Locate the downloaded file: `prompt-enhancer.zip`
2. Right-click → **Extract All** (Windows) or double-click (Mac)
3. You will get a folder named `prompt-enhancer`

### Step 3 — Load into Chrome

1. Open Chrome and go to: `chrome://extensions/`
2. Enable **Developer Mode** (toggle in the top-right corner)
3. Click **"Load unpacked"**
4. Select the extracted `prompt-enhancer` folder
5. The extension icon (⚡) will appear in your Chrome toolbar

> **Microsoft Edge:** Same steps work — go to `edge://extensions/` instead.

### Step 4 — Pin the Extension

1. Click the puzzle piece icon (🧩) in the Chrome toolbar
2. Find **Prompt Enhancer Pro**
3. Click the pin icon 📌 to keep it visible

---

## ⚙️ Setup & Configuration

### Opening the Extension Popup

Click the **⚡ Prompt Enhancer** icon in your Chrome toolbar to open the configuration panel.

### Understanding the Main Screen

```
┌─────────────────────────────────────┐
│ ⚡ Prompt Enhancer PRO         [⚙] │  ← Settings button
├─────────────────────────────────────┤
│ 1→Select  2→Right-click  3→Done  ✓  │  ← Quick guide
├─────────────────────────────────────┤
│  ACTIONS                  2 active  │
│  ●  Enhance Text            [Edit]  │  ← Active action (green dot)
│  ○  Translate to English    [Edit]  │  ← Inactive (no webhook yet)
├─────────────────────────────────────┤
│  [+ Add New Action]                 │
├─────────────────────────────────────┤
│  Right-click menu preview:          │
│  ┌─ ✦ Prompt Enhancer ─────────┐   │
│  │   Enhance Text               │   │
│  │   ─────────────────          │   │
│  │   ⚙ Configure Enhancer…     │   │
│  └──────────────────────────────┘   │
└─────────────────────────────────────┘
```

---

## ➕ Adding Automation Actions

### Create a New Action

1. Click **"+ Add New Action"** in the main popup
2. You will be taken to the **Edit Action** screen

### Configure the Action

```
┌─────────────────────────────────────┐
│ ← Edit Action              [Toggle] │  ← ON/OFF toggle
├─────────────────────────────────────┤
│  Action Name                        │
│  ┌─────────────────────────────┐   │
│  │ e.g. Fix Grammar             │   │
│  └─────────────────────────────┘   │
│                                     │
│  Webhook URL             🔒 Hidden  │
│  ┌─────────────────────────────┐   │
│  │  [Lock icon] Webhook hidden  │   │
│  │  Password: [_____] [Unlock]  │   │
│  └─────────────────────────────┘   │
│                                     │
│  [✓ Save Action]                    │
│  [Delete this action]               │
└─────────────────────────────────────┘
```

**Fields:**

| Field | Description |
|---|---|
| **Action Name** | What appears in the right-click menu (e.g., "Fix Grammar", "Summarize") |
| **Toggle (ON/OFF)** | Enable or disable the action in the context menu |
| **Webhook URL** | Your n8n webhook endpoint URL (password protected) |

### Enable / Disable an Action

- **Toggle ON** → The action appears in the right-click menu (green dot)
- **Toggle OFF** → The action is hidden from the right-click menu but not deleted
- You can toggle at any time by clicking **Edit** → switching the toggle → **Save**

---

## 🔗 Webhook Configuration (n8n)

### What is n8n?

[n8n](https://n8n.io) is an open-source workflow automation tool. You create visual workflows that receive data from the extension, process it with AI, and return the result.

### n8n Workflow Structure

Every automation follows the same simple pattern:

```
[Webhook Trigger]
       ↓
  Receives: { "text": "selected text from browser" }
       ↓
[Your AI Processing Nodes]
  (ChatGPT, Claude, Gemini, custom logic, etc.)
       ↓
[Respond to Webhook]
  Returns: [{ "enhanced": "transformed text" }]
```

### Request Format (sent by extension)

```json
POST https://your-n8n.com/webhook/your-endpoint
Content-Type: application/json

{
  "text": "The text that the user selected on the webpage"
}
```

### Response Format (expected by extension)

The extension accepts all of these response shapes:

```json
[{ "enhanced": "Your transformed text here" }]

// OR
{ "enhanced": "Your transformed text here" }

// OR
[{ "output": "Your transformed text here" }]

// OR
[{ "response": "Your transformed text here" }]

// OR
"Plain text response"
```

### Setting Up a Webhook URL

1. Open your n8n instance
2. Create a new workflow
3. Add a **Webhook** node → set method to `POST`
4. Add your AI processing nodes
5. Add a **Respond to Webhook** node
6. Configure response body:
   ```
   ={{ JSON.stringify([{ "enhanced": $('AI Agent').item.json.output }]) }}
   ```
7. **Activate** the workflow
8. Copy the **Production Webhook URL**
9. Paste it into the extension's webhook field for that action

### Example Workflows

**Text Enhancement (Bengali)**
```
System Prompt: "You are a Bengali text enhancer. Improve the given text 
while keeping the same language and meaning. Return only the enhanced text."
```

**Translate to English**
```
System Prompt: "Translate the given text to English. Make it natural and 
professional. Return only the translated text, nothing else."
```

**Grammar Fixer**
```
System Prompt: "Fix all grammar and spelling mistakes in the given text. 
Keep the same language and meaning. Return only the corrected text."
```

---

## 🔒 Security & Password

### How Webhook Security Works

Webhook URLs are sensitive — they give direct access to your AI backend. Prompt Enhancer Pro **hides all webhook URLs** behind a password:

- URLs are **never visible** when you open the extension
- You must enter the **security password** to view or edit any webhook URL
- The password is stored locally in Chrome's secure storage
- **Default password:** `admin`

### ⚠️ Change Your Password Immediately

> The default password is `admin`. Change it before adding any webhook URLs.

### How to Change Password

1. Click the **⚡ extension icon** to open the popup
2. Click the **⚙ Settings** button (top right)
3. In the **Security Password** section:
   - Enter your **current password** (default: `admin`)
   - Enter your **new password** (minimum 4 characters)
   - **Confirm** the new password
4. Click **"Update Password"**
5. ✅ Password changed successfully

```
┌─────────────────────────────────────┐
│ ← Settings                          │
├─────────────────────────────────────┤
│  SECURITY PASSWORD                  │
│                                     │
│  Current Password                   │
│  [admin          ]                  │
│                                     │
│  New Password                       │
│  [**************]                   │
│                                     │
│  Confirm Password                   │
│  [**************]                   │
│                                     │
│  [Update Password]                  │
└─────────────────────────────────────┘
```

### How to Unlock a Webhook

1. Click **Edit** on any action
2. In the **Webhook URL** section, click the password field
3. Enter your security password
4. Click **"Unlock"**
5. The webhook URL is now visible and editable
6. Click **"Lock again"** when done to re-hide it

---

## 📖 Usage Guide

### Basic Usage (Step by Step)

**Step 1:** Go to any webpage (Google Docs, Facebook, Gmail, any text editor, etc.)

**Step 2:** Select the text you want to transform

```
"আমি বাজারে যাই।"  ← select this
```

**Step 3:** Right-click on the selected text

```
┌──────────────────────────┐
│ Copy                     │
│ Paste                    │
│ ─────────────────────    │
│ ✦ Prompt Enhancer    ▶  │  ← hover here
└──────────────────────────┘
```

**Step 4:** Choose your action from the submenu

```
┌──────────────────────────────┐
│  ✦ Prompt Enhancer           │
│  ├── Enhance Bengali         │  ← click this
│  ├── Translate to English    │
│  ├── Fix Grammar             │
│  ├── ──────────────────      │
│  └── ⚙ Configure Enhancer…  │
└──────────────────────────────┘
```

**Step 5:** Wait for the toast notification

```
✦ Enhance Bengali…    ← processing indicator (bottom-right)
```

**Step 6:** Text is automatically replaced!

```
"আমি প্রতিদিন সকালে তাজা সবজি কিনতে বাজারে যাই।"  ← replaced!
```

### Status Indicators

| Toast | Meaning |
|---|---|
| `✦ Action Name…` (blue) | Processing — waiting for AI response |
| `✓ Done!` (green) | Success — text has been replaced |
| `📋 Enhanced! Press Ctrl+V` (yellow) | Auto-replace failed — text copied to clipboard |
| `❌ Error message` (red) | Something went wrong — check webhook |
| `⚙️ No webhook configured!` (red) | Action has no webhook URL set |

### If Auto-Replace Fails

On some websites (with advanced security), auto-replace may not work. In that case:
1. The enhanced text is **automatically copied to your clipboard**
2. A yellow toast says: `📋 Enhanced! Press Ctrl+V to paste`
3. Simply press **Ctrl+V** to paste the result manually

---

## 🚀 Future Features

Here is what is planned for upcoming versions:

| Feature | Description | Status |
|---|---|---|
| 📊 **Usage Statistics** | Track how many times each action was used | Planned |
| 🕐 **History Log** | View recent transformations with before/after text | Planned |
| 📤 **Export/Import Actions** | Share your action configurations across devices | Planned |
| 🎨 **Custom Icons per Action** | Assign emoji or icon to each action | Planned |
| 🔗 **Multiple Webhooks per Action** | Chain multiple n8n workflows in sequence | Planned |
| 🌐 **Site-Specific Actions** | Show different actions on different websites | Planned |
| 📱 **Firefox Support** | Port extension to Firefox browser | Planned |
| 🔐 **Master Password with PIN** | Numeric PIN option for faster unlocking | Planned |
| 🧩 **Action Templates** | Pre-built action templates for common tasks | Planned |
| 📋 **Clipboard Monitor Mode** | Automatically process copied text | Planned |

Since the backend is powered by **n8n**, you can already build any automation you imagine — AI models (GPT-4, Claude, Gemini), database lookups, API calls, conditional logic, and more. Future extension updates will make it even easier to manage and expand your automations.

---

## ❓ FAQ

**Q: Does the extension work on all websites?**
> Yes. It works on any website including Facebook, Gmail, Google Docs, Twitter/X, TikTok, and local text editors opened in the browser.

**Q: What happens if auto-replace doesn't work?**
> The extension automatically copies the enhanced text to your clipboard. Press Ctrl+V to paste it manually. This happens on websites with very strict security (like some banking sites).

**Q: Is my text sent to any third party?**
> No. Your text is only sent to the webhook URL you configure — which is your own n8n server. Anthropic, Google, or any other third party never sees your data unless your n8n workflow uses their APIs.

**Q: Can I use multiple AI models for different actions?**
> Yes! Each action has its own webhook URL, and each webhook can use a completely different n8n workflow with a different AI model, system prompt, or logic.

**Q: I forgot my security password. What do I do?**
> Go to Settings → **Reset Everything**. This will clear all actions and reset the password to `admin`. You will need to re-add your actions and webhook URLs.

**Q: How many actions can I create?**
> Up to **8 actions** in the current version.

**Q: Do I need to pay for n8n?**
> n8n is open-source and free to self-host. They also offer a cloud version with a free tier. Visit [n8n.io](https://n8n.io) for details.

**Q: Will the extension work if n8n is down?**
> No. The extension requires your n8n server to be running and accessible. If the webhook times out, an error toast will appear.

---

## 🛠️ Technical Details

| Property | Value |
|---|---|
| Manifest Version | V3 |
| Permissions | `storage`, `activeTab`, `scripting`, `tabs`, `contextMenus`, `clipboardWrite` |
| Browser Support | Chrome 102+, Microsoft Edge 102+ |
| Local Storage | Chrome's `chrome.storage.local` API |
| Network | Only connects to your configured webhook URLs |
| Third-party dependencies | None |

---

## 📄 License

MIT License — free to use, modify, and distribute.

---

<div align="center">

Made with ⚡ for productivity

[⬇️ **Download v4.0.0**](https://github.com/mashunterbd/Prompt-enhancer/releases/tag/4.0.0)

</div>
