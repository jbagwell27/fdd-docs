---
order: a
title: Configuring the mod
---

Configuration of the mod is done completely using COMMANDS. These can be executed by players with Permission level 3 (default vanilla OP level).

Below you can find all the commands, as well as what they do.

***

||| Command `maintenance status`
This command displays the current status of the mod. It will be either `true` or `false`
|||

||| Command `maintenance on/off`
Enable or disable maintenance mode
|||

||| Command `maintenance list`
Return a list of users that can join your server during maintenance mode. YOU WILL HAVE TO ADD YOURSELF AS WELL, REGARDLESS OF YOUR PERMISSIONS
|||

||| Command `maintenance reload`
Reload the config, if you edited the config file manually. (The config file is named `mmode.json`)
|||

||| Command `maintenance backup`
Perform a full backup manually
|||

||| Command `maintenance doBackups true/false`
Enable or disable the creation of backups when enabling maintenance mode
|||

||| Command `maintenance setMessage "Your Message Here"`
Set the message to be displayed to the player when they try to join the server during maintenance mode. This might include the planned timeframe, and or other information about the maintenance
|||

||| Command `maintenance addAllowed MinecraftNameHere`
Add a player to the list of allowed players that can join the server during maintenance mode
|||

||| Command `maintenance removeAllowed MinecraftNameHere`
Remove a player from the list of allowed players that can join the server during maintenance mode
|||

||| [!badge Since 1.1] Command `maintenance setMotd Your Message Here`
Change the MOTD that is displayed while the server is in maintenance mode
|||

||| [!badge Since 1.1] Using a different Server Icon when in Maintenance
Since Version 1.1, it's possible to set an alternative icon for your server while in maintenance mode.

To do this, upload another png image of 64x64px (in the same folder as your current server icon) and name it `whateveryoulike.png`.

Next, head over to `config/mmode.json`. Change the value of `maintenanceIcon` to `whateveryoulike.png`.

Finally, execute the command `maintenance reload` to reload the config. Your server will not display this icon when you have maintenance mode enabled
|||

And that's it. More feature/commands will come in the future
