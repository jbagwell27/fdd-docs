# SDLink Basic Mod Setup

This will go through the basics of getting the mod installed with bot status and chat features  

> [!NOTE]
> Before continuing, ensure you have followed the steps to Create and Invite the Discord Bot to your Discord server [Discord Bot Creation](./bot-creation)

## Installing the mod

SDLink requires CraterLib as a dependency. Download and transfer the mod files to the `mods/` folder

*Link to download pages*

At first run an empty config file will be generated: `config/simple-discord-link/simple-discord-link.toml`  
See: [[empty-config]]

## Configuration Settings

### Add the Bot Token

In the `[botConfig]` section, insert the bot token saved from [Empty Config](./empty-config)

```json
[botConfig]
	botToken = "MTE2ODIyMDUyMDM3MDY3OTgzOA.Gjx_DN.1Xl0ZwC63e8sk3Iy9LWDhu2l9DD0oSIr39RcOI"
	#How often the Bot Status will update on Discord (in Seconds). Set to 0 to disable
	statusUpdateInterval = 30
```

This is the identifier for your bot. This token will be encrypted when it's server starts up again.

### Setting the Chat Channel

To get the chat channel ID, right-click on the channel you want chat and events to go and select "Copy Channel ID"<br>![](mod-config1.png)

In the `[channelsAndWebooks.channels]` section paste that ID in the `chatChannelID` field

```json
[channelsAndWebhooks.channels]
	#REQUIRED! The ID of the channel to post in and relay messages from. This is still needed, even in webhook mode
	chatChannelID = "1143258591260856360"
	#If this ID is set, event messages will be posted in this channel instead of the chat channel
	eventsChannelID = "0"
	#If this ID is set, console messages sent after the bot started will be relayed here
	consoleChannelID = "0"
```

This is the bare minimum needed to get the bot up and running with a status
<br>![](mod-config3.png)  
<br>![](mod-config2.png)

For more information on these other fields, see [SDLink Advanced Mod Setup](./advanced-config)

