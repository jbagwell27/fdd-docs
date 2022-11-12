---
title: Understanding the Config
order: a
---
Since this mod relies on Cloth Config and provides a config screen, I would suggest using the config screen to make changes to the config.

However, if it's needed to make manual changes, here is a short explanation of what each option does:

`showProgressText` -> This Enables/Disables the loading/memory text that forge shows on the Loading Screen (FORGE ONLY).

Valid values are `true` or `false`

`progressBarType` -> This controls what type of progress bar is used.

Valid values are `Vanilla, Bossbar, Custom, Logo, Background, Hidden`.

`logoStyle` -> This controls what logo should be shown.

Valid values are `Mojang, Aspect1to1, Hidden`. When set to Aspect1to1, it uses a custom logo of your choice. This logo must be 512px x 512px.

`backgroundImage` -> This controls if the loading screen background is an image or color

Valid values are `true` or `false`

`backgroundColor` -> Here you define what color to use for the loading screen background.

!!!warning
This has no effect when backgroundImage is set to true.
!!!

!!!info
Color values must be in decimal format. If you use the ingame config, it has to be a hex code. You can use this site to help with the conversion: [https://www.mathsisfun.com/hexadecimal-decimal-colors.html](https://www.mathsisfun.com/hexadecimal-decimal-colors.html)
!!!

`progressBarColor` -> Here you can define the color of the progress bar.

!!!warning
This only has effect when progressBarType is set to Vanilla
!!!

!!!info
Color values must be in decimal format. If you use the ingame config, it has to be a hex code. You can use this site to help with the conversion: [https://www.mathsisfun.com/hexadecimal-decimal-colors.html](https://www.mathsisfun.com/hexadecimal-decimal-colors.html)
!!!

`progressFrameColor` -> Here you can define the color of the frame around the progress bar.

!!!warning
This only has effect when progressBarType is set to Vanilla
!!!

!!!info
Color values must be in decimal format. If you use the ingame config, it has to be a hex code. You can use this site to help with the conversion: [https://www.mathsisfun.com/hexadecimal-decimal-colors.html](https://www.mathsisfun.com/hexadecimal-decimal-colors.html)
!!!

`customProgressBarMode` -> This defines if your Custom progress bar texture should be stretched out or clipped to the percent loaded.

Valid values are `Linear` or `Stretch`

!!!warning
This only has effect when the progressBarType is set to Custom
!!!

`customProgressBarBackground` -> This defines if your custom progress bar also has a custom background

!!!warning
This only has effect when the progressBarType is set to Custom
!!!

Valid values are `true` or `false`

#### Textures

!!!warning
This section is about defining your custom images to use. Images must be placed inside your **config/simplesplashscreen** folder
!!!

!!!danger
Images can only be JPG, PNG or GIF. There is currently no support for any other image type.
!!!

`BackgroundTexture` -> This is the name of your Background image to use.

`MojangLogo` -> The logo to use when the logoStyle is set to mojang

`Aspect1to1Logo` -> This is the image to use when logoStyle is set to Aspect1to1. This image must be a 512px x 512px image!

`BossBarTexture` -> This is the image to use when progressBarType is set to Bossbar

`CustomBarTexture` -> This is the image to use for your custom progress bar

`CustomBarBackgroundTexture` -> This is the image to use for your custom progress bar background

You can find out how to properly create these images here: [Creating Custom Images](custom-images.md)
