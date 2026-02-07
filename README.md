# Discord Bot - Voice Chat Disconnection

A Discord bot that can automatically remove users from voice channels at a specified time.

## Features

- `/voicekick` - Schedule automatic disconnection from voice channel at a specific time
- `/ping` - Test bot responsiveness

## Prerequisites

- Node.js 20.17 or higher
- A Discord Bot Token from [Discord Developer Portal](https://discord.com/developers/applications)

## Setup Instructions

### 1. Clone the Repository

```bash
git clone https://github.com/keemuda/discordBot-disconfromvoicechat.git
cd discordBot-disconfromvoicechat
```

### 2. Install Dependencies

```bash
npm install
```

### 3. Configure Environment Variables

1. Copy the example environment file:
   ```bash
   cp .env.example .env
   ```

2. Edit `.env` and add your Discord credentials:
   ```
   DISCORD_TOKEN=your_actual_discord_bot_token
   CLIENT_ID=your_actual_client_id
   ```

   **⚠️ SECURITY WARNING:** 
   - NEVER commit your `.env` file to git
   - NEVER share your Discord bot token publicly
   - Keep your tokens secure and rotate them if exposed

### 4. Register Bot Commands

```bash
node register.js
```

### 5. Run the Bot

```bash
npm start
```

Or with Docker:

```bash
docker build -t discord-bot .
docker run -d --env-file .env discord-bot
```

## Getting Your Discord Credentials

1. Go to [Discord Developer Portal](https://discord.com/developers/applications)
2. Create a new application or select an existing one
3. Go to the "Bot" section to get your `DISCORD_TOKEN`
4. Go to "General Information" to get your `CLIENT_ID`
5. Invite the bot to your server with proper permissions (Voice: Connect, Speak, Move Members)

## Usage

Once the bot is running in your Discord server:

1. Join a voice channel
2. Use `/voicekick time:<time>` command
   - Supported formats: "4 AM", "4:30 PM", "16:00"
   - Example: `/voicekick time:4 AM`
3. The bot will disconnect you from the voice channel at the specified time

## Security Best Practices

✅ **This project follows security best practices:**
- Environment variables are used for all sensitive data
- `.env` file is excluded from git via `.gitignore`
- No hardcoded secrets in source code
- `.env.example` provided as a template

🔒 **Keep your bot secure:**
- Never commit `.env` files
- Rotate tokens immediately if exposed
- Use environment-specific tokens (dev/prod)
- Review bot permissions regularly

## License

ISC

## Author

chayodom
