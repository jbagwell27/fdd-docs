---
title: SDLink Permissions Explained
order: b
---

# SDLink Discord Bot Permissions

Below is a brief description of each Discord permission that SDLink uses

**Required Permissions**:

- Manage Channels
  - Allows for modifying the channel topic for player count and uptime information
- Manage Webhooks
  - Currently unused, but to be used in a future update to allow the bot to create webhooks automatically
- Read Messages/View Channels
  - Allows for messages to be read and sent from Discord -> Minecraft
- Send Messages
  - Allows for messages to be sent from Minecraft -> Discord
- Manage Messages
  - Allows the bot to edit/delete it's own messages: eg. `/playerlist` can auto delete the result
- Embed Links
  - Allows for embed messages such as Join/Leave events.
- Read Message History
  - Helps with reading messages
- Use External Emojis
  - Allows for text emojis to be sent from Minecraft -> Discord: eg. Typing `:rofl:` in game will show up as 🤣 in discord chat
- Use Slash Commands
  - Allows for `/` commands to be used in Discord. Eg, `/playerlist` to see the list of currently active players

**Optional Permissions**:

- Manage Roles
  - Allows you to add a Discord Role to a player when they link their accounts
- Ban Members
  - Allows you to enable a banlist sync which can ban Discord member if their linked MC user was banned in-game
- Mention Everyone
  - Allows for in-game mentions to include `@everyone`
