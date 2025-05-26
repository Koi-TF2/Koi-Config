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

_____________

6. Optional: "Streamer" Mode (Hide usernames) **with Broesel Hud**:
- Hide usernames from the killfeed:
  - Inside `scripts\Hudlayout.res`, find `HudDeathNotice` and change: `"TextFont" "surface11"` to `"TextFont" "redacted8"`. Note that this does not hide weird characters or symbols from player names. If you want to completely remove names fully, use `"TextFont" ""` instead
- Hide usernames/weapon from the killcam:
  - Inside `resource\ui\FreezePanel_Basic.res`, find `FreezeLabelKiller` and change: `"labelText" "%killername%"` to `"labelText" ""`
  - Also inside `resource\ui\FreezePanel_Basic.res`, find `itempanel` and change: `"xpos" "r200"` and `"ypos" "0"` to `"xpos" "9999"` and `"ypos" "9999"` respectively (this prevents the killcam weapon-display itempanel from showing up entirely, so no killcam weapon is shown at all). Note that disabling the killcam itempanel DOES NOT disable the itempanel for both inspecting items manually and inspecting when in the respawn spectate cam (see next bullet for hiding those usernames)
- Hide "\<playername\> is carrying:" text from both manual inspect and respawn spectate cam (allows the weapon to be viewed, but removes the username carrying field):
  - For manual inspect: Locate `resource\ui\HudInspectPanel.res`, find `itempanel` -> `ItemLabel` and change: `"ypos" "3"` to `"ypos" "9999"`
  - For respawn automatic spectate cam inspect: Locate `resource\ui\Spectator.res`, find `itempanel` -> `ItemLabel` and change: `"ypos" "3"` to `"ypos" "9999"`
- Hide usernames from the scoreboard (tab) and spectator list:
  - Inside `resource\ui\ScoreBoard.res`, go to the very bottom of the file and uncomment the large commented-out section (remove the // characters). Uncommenting this section will add big rectangular blocker bars on top of the player names in your scoreboard
- Hide "\<playername\> is on a killstreak" popup notifications:
  - Use "cl_hud_killstreak_display_time 0". The cl_hud_killstreak_display_time cvar can be found in `koi_cfg\hud+ui.cfg` at the top of the file (by default it is set to 3 seconds)
- Hide teammate usernames from the respawn spectate camera xray (the playername above every teammates head through walls during respawn spec cam):
  - Use "tf_spec_xray_disable 1". The tf_spec_xray_disable cvar can be found in `koi_cfg\hud+ui.cfg` at the top of the file (by default it is set to 0 to allow teammate names)
- Hide usernames from the end-of-round MVP top score and top killstreak popup:
  - Inside `resource\ui\WinPanel.res`, find all four of the following: `Player1Name` `Player2Name` `Player3Name` `KillStreakPlayer1Name`, and change: `"font" "surface10"` to `"font" "redacted8"` for all four
- Hide usernames from the casual pre-game round start and post-game stats screens:
  - Pre-game round start screen: Locate `resource\ui\HudMatchStatus.res`, find both `BluePlayerList` and `RedPlayerList`, and change: `"visible" "1"` to `"visible" "0"` for both teams
  - Post-game stats screen: Locate `resource\ui\HudMatchSummary.res`, find both `BluePlayerList` and `RedPlayerList`, and change: `"avatar_width" "s.08"` and `"name_width" "s.19"` to `"avatar_width" "1"` and `"name_width" "1"` respectively for both teams (unfortunately this will still leave the first character of the username, as this is not removable, although it should not matter since the name will still be unreadable)
- Hide usernames from mouse-over/medic:
  - Inside `resource\ui\TargetID.res`, find `TargetNameLabel` and change: `"font" "surface11"` to `"font" "redacted8"`
- Hide usernames from spy disguising:
  - Inside `resource\ui\DisguiseStatusPanel.res`, find `DisguiseNameLabel` and change: `"font" "surface11"` to `"font" "redacted8"`
- Note that changing the above values does not hide player names from textchat/voicechat, so it is recommended to use "commstoggle" with this mode, which toggles on/off both text and voice chat when key pressed. Bound to "\\" (backslash key) by default. Or alternatively open console and type "commstoggle"
- You can optionally hide player's Casual Rank (the icon) from the Tab Scoreboard. Admittedly this is pretty pointless to do, but if you're looking to hide that metric of skill level, then change the following:
  - Inside `resource\ui\ScoreBoard.res`, find `scores` and change: `"medal_width" "28"` and `"medal_column_width" "21"` to `"medal_width" "0"` and `"medal_column_width" "0"` respectively
  - Note that if you are using the scoreboard name-blocker bars, you may also need to manually adjust the bars slightly to the left to compensate for the removal of the medal column (subtract 32 from `"xpos"` but add 32 to `"wide"` on both red and blu blocker bars at bottom of scoreboard file)
- I also suggest checking out the No Hats mod found here: https://pevhs.ch/tf2/vpk/nhbgum/
  - "no_hats_bgum.vpk" is the primary mod that removes cosmetics and works on every server including valve/pure servers. Place the .vpk into `Team Fortress 2\tf\custom`
  - "no_unusuals.vpk" does not work on valve/pure servers, but could still be useful for streamers. Side node, it does not remove the Pro KS Eye-Effect Particles. This mod is not upkept to the same degree as the primary no_hats_bgum.vpk
  - Because the mods listed at this site get updated with new hats and unusual effects many times per year, I suggest keeping them all in their original .vpk file-form, as opposed to extracting the contents. This makes it easier to constantly upgrade them to their new versions when new cosmetic updates drop. Note that if these are outdated (especially the no_unusuals.vpk) they will not work and can cause issues, and as such it may be worthwhile to temporarily disable/delete these mods by removing the .vpk's from your custom folder until they get updated to work with the new content. no_hats_bgum.vpk is typically kept up-to-date very well, while others such as no_unusuals.vpk may lag behind

_____________

7. Optional: Using the custom sprays found within the "Sprays" zip. These can be installed by placing any of the "vgui" folders (1 for each spray) directly into `Steam\steamapps\common\Team Fortress 2\tf\materials` and **NOT** into the "koi_custom" folder's material section (sprays are not meant to be placed into the custom folder). Please note that within `koi_cfg\sprays.cfg`, the variable `cl_logofile "materials/vgui/logos/spray.vtf"` has been pre-set. What this means is only 1 spray named "spray.vtf" can be used at a time. Using multiple sprays and changing between them therefore does not work (unless spray file is renamed or config is changed).

_____________

8. Note 1: When viewing other player's demo files (.dem), make sure your `config.cfg` file is set to Read-Only. Doing so will prevent the other player's custom settings seen within the demo file from being placed into your own game files, potentially overwriting config settings. This will not impact viewing your own demos since they only utilize your own settings.

9. Note 2: Sometime in 2021 RGL made any "oversized heal particles" illegal. Because of this ban, I have created a custom rule-friendly overheal particle which turns the default stock overheal particles bright green for higher visibility. They are completely stock and not oversized, only the color has been changed for better visibility. This rule-friendly particle file is used by default with this config. Please note that I have still included the previous large overheal particles in this config in a backup folder located here `koi_custom\particles\BACKUP\` in case anyone wants to use them. As a reminder: if you do choose to use the oversized particles in RGL, I am not responsible for issues you may run into with the admins - this is your warning. If RGL decides to allow the large particles again then I will remove this note from this readme and make the large particles default again.
