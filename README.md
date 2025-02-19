 ```
  ___   ___     __________    ___        ________   ________   ________      
 |\  \ |\  \   |\   ____  \  |\  \      |\   ____\ |\  _____\ |\   ____\     
 \ \  \/   /|_ \ \  \__|\  \ \ \  \     \ \  \___| \ \  \___| \ \  \___|     
  \ \   ____  \ \ \  \ \ \  \ \ \  \     \ \  \     \ \   __\  \ \  \  ___   
   \ \  \__ \  \ \ \  \_\_\  \ \ \  \     \ \  \____ \ \  \_|   \ \  \|\  \  
    \ \__\ \ \__\ \ \_________\ \ \__\     \ \______\ \ \__\     \ \_______\ 
     \|__|  \|__|  \|_________|  \|__|      \|______|  \|__|      \|_______| 

```
_____________

### Download: https://github.com/Koi-TF2/Koi-Config/archive/refs/heads/Release.zip

#### Current version: 6.8.1 (Feb 19th, 2025)

_____________

##### HOW TO INSTALL:
1. Copy the "koi_cfg" folder, "autoexec.cfg" file, "config.cfg" file, and "listenserver.cfg" into TF2's default "cfg" folder. (Location for the default cfg folder is `Steam\steamapps\common\Team Fortress 2\tf\cfg`)

2. Copy the "koi_custom" folder into TF2's default "custom" folder. (Location for the default custom folder is `Steam\steamapps\common\Team Fortress 2\tf\custom`)

3. Add the "Advanced launch options" through steam. To do this: 
   - Find TF2 in your steam library
   - Right click on the game, and then click on "Properties"
   - Under the "General" tab, you will see a "Set Launch Options" area
   - Paste in the line of launch options seen below into that area, and then click OK
 - #### Fullscreen 16:9 @ 1920x1080 240hz: 
`-dxlevel 95 -full -w 1920 -h 1080 -freq 240 -novid -nojoy -nosteamcontroller -nohltv -noquicktime -precachefontchars -useforcedmparms -noforcemaccel -noforcemspd -no_texture_stream`
 - #### Fullscreen 4:3 @ 1440x1080 240hz: 
`-dxlevel 95 -full -w 1440 -h 1080 -freq 240 -novid -nojoy -nosteamcontroller -nohltv -noquicktime -precachefontchars -useforcedmparms -noforcemaccel -noforcemspd -no_texture_stream`
- For 4:3 Stretched support, make the following adjustments:
  - Inside of NVidia Control Panel, locate: `Display -> "Adjust desktop size and position" -> Choose your primary monitor -> "Apply the following settings:" for "Scaling" -> Full-screen`. Depending on the PC being used, you may also need to tick the `"Override the scaling mode set by games and programs"` box in the same section.
  - Recommended but optional: Inside `koi_cfg\mouse+sens.cfg`, change the "m_yaw" cvar from `m_yaw 0.022` to `m_yaw 0.0165`. This ensures that the horizontal sensitivity matches with the vertical sensitivity when display is stretched.
 - #### Windowed Borderless 16:9 @ 1920x1080 240hz (Much better alt+tab support): 
`-dxlevel 95 -sw -w 1920 -h 1080 -noborder -freq 240 -novid -nojoy -nosteamcontroller -nohltv -noquicktime -precachefontchars -useforcedmparms -noforcemaccel -noforcemspd -no_texture_stream`
  


4. **HIGHLY RECOMMENDED - IMPORTANT**: Install Broesel Hud & the Broesel Hud Customizations. To do this:
   - Prerequisites:
     1) Have the "koi_custom" folder already installed
     2) Extract the Broesel Hud zip archive found in this repo. The version from this repo contains a few minor fixes and adjustments not present in the 'official' repo
   - After both above prerequisites are complete: Install the hud. From the main "Broesel Hud" folder inside the hud zip, there will be a "resource" and "scripts" folder. Drag both into the `koi_custom` folder. When prompted, choose to **replace the existing files** that have the same names so that the Broesel Hud files overwrite the existing ones.
   - Once Broesel Hud is installed, install the items in the "Broesel Hud Customizations" folder from the hud zip. Inside this folder there are numbered customization folders which are HIGHLY RECOMMENDED. To make the install process quick and easy, there is also an `ALL-QUICK` folder with all recommended customizations inside ready to be added. Drag the cooresponding "scripts", "materials", and "resource" folders into the `koi_custom` folder. Similarly to the previous step, choose to replace the existing files so that the customization files overwrite the existing ones.
 - #### If you are not using Broesel Hud, please read the following notes:
   - NOTE 1: "tf_hud_target_id_disable_floating_health" needs to be set to "1" when using Broesel Hud. **It is already set to 1 by default in this config**. If you are NOT using Broesel Hud then keep this on 0. It can be found in `koi_cfg\hud+ui.cfg` at the very top of the file, just in case.
   - NOTE 2: The Broesel Hud Customizations include a custom crosshair. If you do not use the Broesel Hud Customizations, you will need to re-enable the regular game crosshair. To do so, go to `koi_cfg\crosshair.cfg` and change the "cl_crosshair_scale" value to "28". Additionally, you will need to go to `koi_cfg\enhancements\zoom_toggle.cfg` and change the values of "cl_crosshair_scale" to "12" on zoomin and "28" on zoomout. All of these scale values have been set to 0 by default so that the built-in crosshair is not visible (so as to not have the default game crosshair collide with the custom crosshair).

_____________

5. Optional but Recommended: Set an sv_password on the local listen server creation (inside of `listenserver.cfg`). By default, there is no password set. This config sets all necessary configurations to allow local server creation (like with the map command, or with the Create Server button) to use Steam Networking (Steam Datagram Relay) to automatically handle internet traffic. This means any listen server you generate will securely allow outside players to find your game inside of the Internet tab of the Server Browser, since it is assigned a "fake" SDR IP using secure Steam Networking. If you do not want players being able to connect to your listen servers, you should either set sv_password to something nobody can guess, or change the values for sv_lan to 1 in both `koi_cfg\network.cfg` and `listenserver.cfg`. Setting sv_lan 1 will disable internet traffic to the listen server entirely, regardless of Steam Networking. Keeping sv_lan 0 and setting sv_password will let the listen server show in the browser but block incoming connections unless the player knows the password you set to your listen server

6. Optional: "Streamer" Mode (Hide usernames) **with Broesel Hud**:
- Hide usernames from the killfeed:
  - Inside `scripts\Hudlayout.res`, find `HudDeathNotice` and change: `"TextFont" "surface11"` to `"TextFont" "redacted8"`. Note that this does not hide weird characters or symbols from player names. If you want to completely remove names fully, use `"TextFont" ""` instead
- Hide usernames from the killcam:
  - Inside `resource\ui\FreezePanel_Basic.res`, find `FreezeLabelKiller` and change: `"labelText" "%killername%"` to `"labelText" ""`
  - Also inside `resource\ui\FreezePanel_Basic.res`, find `itempanel` and change: `"xpos" "r200"` and `"ypos" "0"` to `"xpos" "9999"` and `"ypos" "9999"` respectively (this prevents the killcam weapon-display panel from showing up, which contains "\<playername\> is carrying:". This also prevents malicious weapon names/descriptions from being displayed on killcam. Note that this DOES NOT disable the item inspect/display panel entirely - you can still inspect and see other player's items in spectate and while waiting for respawn. This ONLY disables being able to see the weapon of the player who killed you within the killcam specifically)
- Hide \<playername\> is on a killstreak popup notifications:
  - Use "cl_hud_killstreak_display_time 0". The cl_hud_killstreak_display_time cvar can be found in `koi_cfg\hud+ui.cfg` at the top of the file (by default it is set to 3 seconds)
- Changing these values does not hide player names from the scoreboard (tab), from voicechat, or from friendly medics/friendly players when moused-over
- It is recommended to use "commstoggle" with this mode, which toggles on/off both text and voice chat when key pressed. Bound to "\\" (backslash key) by default. Or alternatively open console and type "commstoggle"
- You can optionally hide player's Casual Rank (the icon) from the Tab Scoreboard. Admittedly this is pretty pointless to do, but if you're looking to hide that metric of skill level, then change the following:
  - Inside `resource\ui\ScoreBoard.res`, find `scores` and change: `"medal_width" "28"` and `"medal_column_width" "21"` to `"medal_width" "0"` and `"medal_column_width" "0"` respectively
- I also suggest checking out the No Hats mod found here: https://pevhs.ch/tf2/vpk/nhbgum/
  - "no_hats_bgum.vpk" is the primary mod that removes cosmetics and works on every server including valve/pure servers. Place the .vpk into `Team Fortress 2\tf\custom`
  - "no_unusuals.vpk" does not work on valve/pure servers, but could still be useful for streamers. Side node, it does not remove the Pro KS Eye-Effect Particles. This mod is not upkept to the same degree as the primary no_hats_bgum.vpk
  - Because the mods listed at this site get updated with new hats and unusual effects many times per year, I suggest keeping them all in their original .vpk file-form, as opposed to extracting the contents. This makes it easier to constantly upgrade them to their new versions when new cosmetic updates drop. Note that if these are outdated (especially the no_unusuals.vpk) they will not work and can cause issues, and as such it may be worthwhile to temporarily disable/delete these mods by removing the .vpk's from your custom folder until they get updated to work with the new content. no_hats_bgum.vpk is typically kept up-to-date very well, while others such as no_unusuals.vpk may lag behind

7. Optional: Using the custom sprays found within the "Sprays" zip. These can be installed by placing any of the "vgui" folders (1 for each spray) directly into `Steam\steamapps\common\Team Fortress 2\tf\materials` and **NOT** into the "koi_custom" folder's material section (sprays are not meant to be placed into the custom folder). Please note that within `koi_cfg\sprays.cfg`, the variable `cl_logofile "materials/vgui/logos/spray.vtf"` has been pre-set. What this means is only 1 spray named "spray.vtf" can be used at a time. Using multiple sprays and changing between them therefore does not work (unless spray file is renamed or config is changed).

_____________

8. Note 1: When viewing other player's demo files (.dem), make sure your `config.cfg` file is set to Read-Only. Doing so will prevent the other player's custom settings seen within the demo file from being placed into your own game files, potentially overwriting config settings. This will not impact viewing your own demos since they only utilize your own settings.

9. Note 2: Sometime in 2021 RGL made any "oversized heal particles" illegal. Because of this ban, I have created a custom rule-friendly overheal particle which turns the default stock overheal particles bright green for higher visibility. They are completely stock and not oversized, only the color has been changed for better visibility. This rule-friendly particle file is used by default with this config. Please note that I have still included the previous large overheal particles in this config in a backup folder located here `koi_custom\particles\BACKUP\` in case anyone wants to use them. As a reminder: if you do choose to use the oversized particles in RGL, I am not responsible for issues you may run into with the admins - this is your warning. If RGL decides to allow the large particles again then I will remove this note from this readme and make the large particles default again.
