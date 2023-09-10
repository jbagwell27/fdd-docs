---
title: Creating the Discord Bot
order: a
---

Simple Discord Link requires a Discord Bot, or Discord Application to function. Even if you already have a discord bot/application set up, follow through this guide to make sure the setup is still correct.

!!!danger Do not skip any steps
A common problem users run into, is skipping a vital step of this set up. Specifically, the second step of part 2. PLEASE read the docs thoroughly, to avoid any problems later on
!!!

***

## Part 1 - Creating the discord Application

To get started, head over to https://discord.com/developers and sign in using your Discord account. After sign in, you will be greeted by the Discord Developer Dashboard.

Press the "New Application" button, located at the top right of the screen (see screenshot below).

![Discord Developers Portal](https://cdn.firstdark.dev/docs/sdlink-wiki/bot_step1.png)

&nbsp;

You will then be greeted by the "Create an Application" dialog. On this dialog, you will need to enter the name of your bot/application and accept the Discord terms and conditions.

!!!warning Notice about names
The name of your discord bot/application CANNOT include the word `Discord`. This will cause problems, and will cause your bot not to start up
!!!

![Create Application Dialog](https://cdn.firstdark.dev/docs/sdlink-wiki/bot_step2.png)

&nbsp;

Once you have created your app, you will be shown the "General Information" screen. Here you can upload an icon for your application and optionally, give your bot a description. The description will be shown in the "About" section of the bot profile in discord.

![General Information Screen](https://cdn.firstdark.dev/docs/sdlink-wiki/bot_step3.png)

***

## Part 2 - Set up the bot

!!!danger DO NOT SKIP THIS PART
These steps are very important. This is where most users screw up, and then their bots fail to function
!!!

Click on "Bot", on the navigation menu on the left. This will open the Bot page of your application. This is where you will get your bot token.

![Bot Screen](https://cdn.firstdark.dev/docs/sdlink-wiki/bot_step4.png)

Here, you want to click on "Reset Token". This will generate a new discord bot token for you. Copy this token into notepad, or somewhere you can reach it again, as you will need it later in the mod config.

!!!danger KEEP THIS TOKEN PRIVATE
If you leak this token, anyone can run a bot impersonating yours, that could do basically anything it wants. The token will be encrypted in the config as well, to prevent accidental leakage when sharing your config.
!!!

&nbsp;

### The very important part

On the same screen where you found your bot token, scroll down until you see a bunch of switches.

![Bot Screen 2](https://cdn.firstdark.dev/docs/sdlink-wiki/bot_step5.png)

On this screen you need to:

1) Disable Public Bot. This will prevent other people aside from you, inviting the bot to their discords, using your invite link from the logs.
2) Enable the Presence intent. This is required so that the bot can detect users leaving and joining your discord.
3) Enable the Server Members intent. This is required so that the bot can interact with users in your discord server.
4) Enable the message content intent. Without this, the bot will not be able to relay messages from Discord to Minecraft.


If you do not enable 2-4, your bot will fail to start. This is one that so many users mess up, so please double check this!