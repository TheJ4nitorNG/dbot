# DISCBOT

This is the template bot file for the SCP Roblox Server. Edit **const systemPrompt = `YOURTEXTFILE.txt** and add the *personality/brain* for the bot.

He is powered by **Gemini 2.x** (`gemini-2.5-flash`) via the modern `@google/genai` SDK and integrated with Discord using `discord.js` v14.

---

## 🚀 Quick Start Guide

### 1. Prerequisites
Make sure you have the following installed on your machine:
* **Node.js** (v18.0.0 or higher is required for `discord.js` v14)
* **npm** (comes packaged with Node.js)

---

### 2. Set Up Your Discord Bot
To get your bot token and invite the bot to your server, follow these steps:

1. Go to the [Discord Developer Portal](https://discord.com/developers/applications).
2. Click **New Application** in the top right corner and name your bot (e.g., "Terri").
3. Navigate to the **Bot** tab on the left sidebar.
4. Scroll down to the **Privileged Gateway Intents** section and **enable**:
   * **Message Content Intent** (⚠️ **CRITICAL**: The bot cannot read mentions or messages without this!)
   * *Optional but recommended:* **Server Members Intent** and **Presence Intent**.
5. Scroll back up to the **Token** section, click **Reset Token**, and copy the token string. **Keep this secret!** (This will be your `DISCORD_TOKEN`).
6. Navigate to the **OAuth2** -> **URL Generator** tab on the left sidebar:
   * Under **Scopes**, select `bot`.
   * Under **Bot Permissions**, select:
     * *Read Messages/View Channels*
     * *Send Messages*
     * *Read Message History*
     * *Use External Emojis*
7. Copy the generated URL at the bottom of the page, paste it into your browser, and authorize the bot to join your target server.

---

### 3. Set Up Your Gemini API Key
Bot uses the Google Gemini API to generate its responses

1. Go to [Google AI Studio](https://aistudio.google.com/).
2. Click **Get API Key** and create a new API key.
3. Copy the API key string. **Keep this secret!** (This will be your `GEMINI_API_KEY`).


---

### 4. Project Configuration (`.env`)
In the root directory of the project, where index.js lives, create or open the `.env` file and populate it with your credentials:

```env
DISCORD_TOKEN=your_discord_bot_token_here
GEMINI_API_KEY=your_gemini_api_key_here
```

---

### 5. Install Dependencies & Run
Once your configuration is complete, run the following commands in your terminal:

```bash
# Install the required packages (discord.js, @google/genai, dotenv)
npm install

# Start the bot
node index.js
```

When successful, you'll see this print to the console:
```text
BOT Is Online
```

---

## Bot's Personality & Triggers
To get the full "bot experience" on your server, make sure to interact with him knowing his core rules:

* **How to Talk to Him:** You can talk to him in a few different ways:
  1. **Mention/ping him** directly (e.g., `@Bot hello`).
  2. **Say his name** ("Terri") anywhere in the message (case-insensitive, e.g., `Hey Bot you smell funny`).
  3. **Reply to his messages** directly using Discord's reply function (no tag needed!).
  He will ignore other messages and messages from other bots.


---

## 🛠️ Tech Stack Details
* **Runtime:** Node.js (v18+)
* **Discord Library:** `discord.js` (v14.26.4)
* **LLM Client:** `@google/genai` (v2.10.0)
* **Model:** `gemini-2.5-flash`
