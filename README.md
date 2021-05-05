Download: https://github.com/Koi-Code-TF2/Koi-Config/archive/refs/heads/main.zip

HOW TO INSTALL:
1. Copy both the "koi_cfg" folder and the "autoexec.cfg" file into TF2's default "cfg" folder. 

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

4. RECOMMENDED/OPTIONAL: Install Broesel Hud & the customizations. To do this:
   - Prerequisites: 1) have the “koi_custom” installed. 2) Download Broesel Hud from an official hud source website, it is not included in this repo. 
   - After both above prerequisites are complete: drag the Broesel Hud “resource” and “scripts” folders into the koi_custom folder (not the customization files from this repo - that step comes next). When prompted, choose to replace the existing files that have the same names so that the Broesel Hud files overwrite the existing ones.
   - Install the custom Broesel Hud Customizations. These customizations are included in this repo in the “broesel hud customizations” folder. There are three total customizations. For each of the three, drag the “scripts”, “materials”, “resource” folders into the koi_custom folder and similarly to the above step choose to replace the existing files so that the customization files overwrite the existing ones.
   - Set "tf_hud_target_id_disable_floating_health 1". This value should be set to 1 for best results when using Broesel Hud. This value can be found in "koi_cfg/hud+ui.cfg" at the top of the file.
