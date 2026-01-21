# Discord Birthday Wishes

Automatically sends birthday messages to friends in a Discord server using GitHub Actions.

<img width="100%" alt="Example of the output seen in the discord server" src="https://github.com/user-attachments/assets/45f99b8f-b3e9-4889-9de9-6340e1bba42b" />

## How It Works

A scheduled GitHub Action runs daily at 06:10 UTC and checks if anyone has a birthday. If it's someone's birthday, a message is sent to Discord with their mention and a random birthday wish.

## Setup

1. **Add a Discord webhook**
   - Create a webhook in your Discord server
   - Add it as a repository secret named `DISCORD_WEBHOOK_URL`

2. **Configure birthdays**
   - Edit the matrix in [.github/workflows/check-birthdays.yml](.github/workflows/check-birthdays.yml)
   - Add entries with name, birthday (MM-DD format), and Discord ID

3. **Customize messages**
   - Edit [messages.yml](messages.yml) to add or modify birthday messages
   - Use `{MENTION}` as a placeholder for the Discord mention

## Configuration

The workflow can be customized by editing environment variables at the top of [check-birthdays.yml](.github/workflows/check-birthdays.yml):

- `BOT_NAME` - Name displayed in Discord
- `BOT_AVATAR_URL` - Avatar image URL
- `EMBED_COLOR` - Hex color for the embed
- `THUMBNAIL_URL` - Thumbnail image URL
- `FROM` - Footer text

## Manual Trigger

The workflow can be manually triggered from the Actions tab if needed.
