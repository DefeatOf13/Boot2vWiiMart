# WiiMart Forwarder WUHB

Boots the WiiMart channel and skips all Wiimote prompts! This is meant to be used with Aroma.
**⚠️⚠️⚠️ This is NOT a "VC inject". It's a simple forwarder that uses official Nintendo functions. Therefore it will NEVER support VC inject features like "controlling the channel with the GamePad". ⚠️⚠️⚠️**

## How to build
1. Install the current versions of devkitPPC, wut and wut-tools
2. Run `make` to compile the title
3. Copy the resulting `wuhb` to `SD://wiiu/apps/`

Just specify them as compile time options after `make`! Supported parameters are:

- `APP_NAME`: Name of the title in the Wii U Menu (defaults to `Boot2vWii`)
- `APP_SHORTNAME`: Short app name, if needed
- `APP_AUTHOR`: Homebrew author
- `ICON`: Path to a 128x128 PNG used as Wii U Menu icon
- `TV_SPLASH`: Path to a 1280x720 PNG used as the TV's splash screen
- `DRC_SPLASH`: Path to a 854x480 PNG used as the Wii U GamePad's splash screen
- `TID`: Title ID of the channel that you want to boot (defaults to `0`, the Wii Menu)
- `DISPLAY_ON`: Display mode of the booted vWii channel. Supported modes are: `TV`, `DRC` (GamePad) or `BOTH` (defaults
  to `BOTH`). Note that it falls back to the GamePad if no TV is connected.
- `FORCERES`: Forces resolution when booting a vWii channel. Supported modes are: `NONE`, `P720` or `P480` (defaults
  to `NONE`). Note that it only works with HDMI.

  ### Example
    ```
    make APP_NAME="WiiMart" ICON="icon.png" TV_SPLASH="assets/bootTvTex.png" DRC_SPLASH="assets/bootDrcTex.png"
    ```
