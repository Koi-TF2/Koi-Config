### Download: https://github.com/Koi-TF2/Koi-Config/archive/refs/heads/main.zip

#### Current version: 5.5 (February 12th, 2022)

_____________

##### HOW TO INSTALL:
1. Copy the "koi_cfg" folder, the "autoexec.cfg" file, and the "config.cfg" file into TF2's default "cfg" folder. 

   (Default location for the cfg folder is "Steam\steamapps\common\Team Fortress 2\tf\cfg")

2. Copy the "koi_custom" folder into TF2's default "custom" folder. 

   (Default location for the custom folder is "Steam\steamapps\common\Team Fortress 2\tf\custom")

3. Add the "Advanced launch options" through steam. To do this:
   - Find TF2 in your steam library
   - Right click on the game, and then click on "Properties"
   - Under the "General" tab, you will see a "Set Launch Options" area
   - Paste in the line of launch options seen below into that area, and then click OK

  Advanced launch options (copy+paste):
  
  -dxlevel 95 -sw -w 1920 -h 1080 -noborder -novid -useforcedmparms -noforcemaccel -noforcemspd

_____________

4. <span style="text-decoration: underline">HIGHLY RECOMMENDED</span>: Install Broesel Hud & the Broesel Hud customizations. To do this:
   - Prerequisites: 1) have “koi_custom” installed. 2) Open the Broesel Hud zip archive found in this repo (or alternatively download Broesel Hud from an official hud source website i.e. https://huds.tf/site/s-Broesel-Hud).
   - After both above prerequisites are complete: from the main Broesel Hud files, you will need the “resource” and “scripts” folders. Drag both into the "koi_custom" folder. When prompted, choose to replace the existing files that have the same names so that the Broesel Hud files overwrite the existing ones.
   - Once Broesel Hud is installed, install the Broesel Hud customizations found within this repo in the “broesel hud customizations” folder. There are three customizations I HIGHLY RECOMMEND installing, the fourth one being optional and not necessary. The three HIGHLY ENCOURAGED ones are "Crosshair", "Health Cross", and "Main Menu". For each of the three, drag the cooresponding “scripts”, “materials”, and “resource” folders into the "koi_custom" folder. Similarly to the previous step, choose to replace the existing files so that the customization files overwrite the existing ones.
   - Make sure "tf_hud_target_id_disable_floating_health 1" is set. This value should be set to 1 for best results when using Broesel Hud. It can be found in "koi_cfg/hud+ui.cfg" at the top of the file and is set to 1 by default. If you are NOT using Broesel Hud then it may be better to keep this on 0.

5. HIGHLY RECOMMENDED: When viewing other player's demo files (.dem), make sure your "config.cfg" file is set to Read-Only. Doing so will prevent the other player's custom settings seen within the demo file from being placed into your own game files, potentially overwriting config settings. This will not impact viewing your own demos since they only utilize your own settings.

_____________

6. Optional: Using the custom sprays found within the "sprays" folder. These can be installed by placing any of the "logos" folders (1 for each spray) directly into "Steam\steamapps\common\Team Fortress 2\tf\materials\vgui" and NOT into the "koi_custom" folder's material section (sprays are not meant to be placed into the custom folder). Please note that within the "sprays.cfg" file in "koi_cfg", the variable cl_logofile "materials/vgui/logos/spray.vtf" has been pre-set. What this means is only 1 spray named "spray.vtf" can be used at a time. Using multiple sprays and changing between them is not advised since the names will vary.
