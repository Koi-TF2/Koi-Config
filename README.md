### Download: https://github.com/Koi-TF2/Koi-Config/archive/refs/heads/Release.zip

#### Current version: 5.8.1 (April 9th, 2022)

_____________

##### HOW TO INSTALL:
1. Copy the "koi_cfg" folder, "autoexec.cfg" file, and "config.cfg" file into TF2's default "cfg" folder. (Location for the default cfg folder is `Steam\steamapps\common\Team Fortress 2\tf\cfg`)

2. Copy the "koi_custom" folder into TF2's default "custom" folder. (Location for the default custom folder is `Steam\steamapps\common\Team Fortress 2\tf\custom`)

3. Add the "Advanced launch options" through steam. To do this: 
   - Find TF2 in your steam library
   - Right click on the game, and then click on "Properties"
   - Under the "General" tab, you will see a "Set Launch Options" area
   - Paste in the line of launch options seen below into that area, and then click OK
  
  #### Advanced launch options (copy+paste): `-dxlevel 95 -sw -w 1920 -h 1080 -noborder -novid -useforcedmparms -noforcemaccel -noforcemspd`
  

4. **HIGHLY RECOMMENDED - IMPORTANT**: Install Broesel Hud & the Broesel Hud Customizations. To do this:
   - Prerequisites: 1) have the "koi_custom" folder already installed. 2) extract/open the Broesel Hud zip archive found in this repo.
   - After both above prerequisites are complete: Install the hud. From the main "Broesel Hud" folder inside the hud zip, there will be a "resource" and "scripts" folder. Drag both into the "koi_custom" folder. When prompted, choose to **replace the existing files** that have the same names so that the Broesel Hud files overwrite the existing ones.
   - Once Broesel Hud is installed, install the items in the "Broesel Hud Customizations" folder from the hud zip. Inside this folder there are three numbered customizations which are HIGHLY RECOMMENDED. For each of the three, drag the cooresponding "scripts", "materials", and "resource" folders into the "koi_custom" folder. Similarly to the previous step, choose to replace the existing files so that the customization files overwrite the existing ones.
   - NOTE: "tf_hud_target_id_disable_floating_health" needs to be set to "1" when using this hud. **It is already set to 1 by default in this config**. If you are NOT using Broesel Hud then it may be better to keep this on 0. It can be found in "koi_cfg/hud+ui.cfg" at the very top of the file, just in case.

_____________

5. Optional: Using the custom sprays found within the "Sprays" zip. These can be installed by placing any of the "vgui" folders (1 for each spray) directly into `Steam\steamapps\common\Team Fortress 2\tf\materials` and **NOT** into the "koi_custom" folder's material section (sprays are not meant to be placed into the custom folder). Please note that within the "sprays.cfg" file in "koi_cfg", the variable cl_logofile "materials/vgui/logos/spray.vtf" has been pre-set. What this means is only 1 spray named "spray.vtf" can be used at a time. Using multiple sprays and changing between them therefore does not work (unless spray file is renamed or config is changed).

_____________

6. Note 1: When viewing other player's demo files (.dem), make sure your "config.cfg" file is set to Read-Only. Doing so will prevent the other player's custom settings seen within the demo file from being placed into your own game files, potentially overwriting config settings. This will not impact viewing your own demos since they only utilize your own settings.

7. Note 2: For some unclear reason, as of sometime in 2021 RGL has made any (in vague terms) "oversized heal particles" illegal. I disagree with this rule, and to my knowledge RGL is the only league enforcing this ban. Because of this, I have still included the large overheal particles in this config by default. If you are concerned that RGL will pursue action because of these particles then I strongly advise not using them during official RGL matches to be 100% safe. I am not responsible for issues you may run into with RGL - this is your warning. To avoid this, move/remove the large overheal particle file `Steam\steamapps\common\Team Fortress 2\tf\custom\koi_custom\particles\medicgun_attrib.pcf`. You can put the particle file back in the config when you aren't playing an official RGL match. If RGL decides to allow these particles again (which they should) then I will remove this note from this readme.
