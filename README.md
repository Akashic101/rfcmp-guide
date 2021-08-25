# HOW TO CREATE AN RFCMP-MOD FOR RFACTOR 2 – THE BETTER GUIDE

## Parade lap

This guide is not for everyone but more for myself. In this guide I will break down how to create a mod-package for rFactor 2 since the [official guide](https://docs.studio-397.com/users-guide/custom-liveries-how-to-make-an-update-rfcmp-for-league-use) is lacking in certain parts. A mirror of this guide will also be published on my website and can be found [here](https://davidmoll.net/2021/08/25/how-to-create-an-rfcmp-mod-for-rfactor-2-the-better-guide/)

## Green lights

First you need a minimum of one file per team, the main .dds-file. Other files that are optional are:

* teamname.json
* teamname_region.dds
* teamnameWINDOW.dds (The official guide says the name should be WINDOWIN instead of WINDOW. More testing is required which version is correct or if both work

For better management I also prefer to set up a few folders so everything has each designated area. The folder-structure I prefer looks like this (with example-names). Some file-names might not make sense yet but will be explained later in this guide:

* Endurance Race
	* Teams
  		* Team 1
			* Team1.dds
			* Team1_region.dds
  			* Team1.veh
  		* Team 2
  			* Team2.dds
   			*Team2.json
  			* Team2.veh
	* Upgrade
    	* car1-upgrade.ini
    	* car2-upgrade.ini
	* MAS
		* Car 1 MAS
    		* car1.mas
		* Car 2 MAS
    		* car2.mas
	* rfcmp
    	* car1.rfcmp
    	* car2.rfcmp

First we need to create the .veh file for each team. This one contains information about the livery used, the car number, team- and driver-name and more. To get this file you first need to open MAS2.exe which is by default in `C:\Program Files (x86)\Steam\steamapps\common\rFactor 2\Support\Tools`. I prefer to use the _x64.exe version but both versions should work.

After you opened the program navigate in the explorer to the path were you installed rFactor 2. For me this is at `C:\Program Files (x86)\Steam\steamapps\common\rFactor 2`. There, navigate to `/Installed/Vehicles` and go to the car you want to create a mod for. In this folder you might find multiple versions of the car. Let’s pick as an example the Oreca 07 LMP2 2017. It has two versions, 2.18 and 2.19. Pick whatever folder has the highest number excluding already created mods for this car (in this case 2.19). In his folder you will find the `car-upgrade.mas` file. Drag this file into MAS2. There you need to grab any of the .veh-files. Right-click on it and export it to “Event name/Teams/Teams 1”.

![location of .veh file](https://davidmoll.net/wp-content/uploads/2021/08/15_16_25_08_2021_gMotor2_MAS_File_Utility_-_car-upgrade.mas_37875-1024x501.png)

The next step is to open this file in your preferred text-editor. Locate the following lines and edit them so they match your teams info (marked with comments). The only info that is a must is the DefaultLivery which should have the exact same name as the .dds file of the teams livery.

### Do not change the MaterialOverride!

```json
DefaultLivery=”team1.dds” //replace with the name of the main .dds file
MaterialOverride=”Oreca_07_BaseMat.json”

Number=33 //replace with the drivers number
Team=”Team 1“ //replace with the teams name
PitGroup=”Group1″
Driver=”David Moll“ //replace with the drivers name
Description=”Oreca 07 #33“ //replace number with the drivers number
Engine=”5.5l V8″
Manufacturer=”Oreca”

Classes=”DPi, LMP2, LMP2_Oreca_07, LeMans24HV”

FullTeamName=”Team 1 Motorsports“ //replace with the teams full name
TeamHeadquarters=”Germany“ //replace with the teams location

Category=”Oreca, Oreca 07″
```

Create this file for each team. Make sure to use the correct .veh-file for each car, every file is slightly different to each other. For example edit the .veh file of the Oreca but don’t use it for the Ferrari 488 GTE. For this you need to open it’s own car-upgrade.mas file and extract an .veh file to edit it.

## Pit-stop

For the next step you will need an additional file for each car. Open again the car-upgrade.mas-file, sort by Type and locate the upgrades.ini file. For the Oreca it is named `Oreca_07_Upgrades.ini`. Extract this into `Event name/Upgrade`. Do this for each car included in the mod.

Next up we create the .mas file for each car. For this click the empty-page symbol in MAS2 so no files are shown anymore. Then grab each file you have for this car and drag it into the program. Also include the upgrades.ini file. If you have multiple teams driving the same car you also need to create those here. The upgrades.ini file needs to be only included once. If you have added all the files you need to click on the 5th button as shown in the image below to create the MAS file. Save this file in `Event name/Car 1 MAS`. Do this for every car and remember to use the correct `upgrades.ini` file, each car has a different one.

In case you have teams driving default liveries you also need to include those. For that you need to open the .MAS-file of the car you used to extract the upgrades.ini and .veh file and add your files there instead of in a blank window. Keep in mind that the file-size will be multiple times of the version without the default liveries included.

![Create the MAS file](https://davidmoll.net/wp-content/uploads/2021/08/15_43_25_08_2021_gMotor2_MAS_File_Utility_-_Untitled_20371-1024x185.png)

## Last lap

First you need to open the folder of the car and note the last even numbered version, in case of the Oreca 2.18.

Navigate to the rfcmp-folder and create a new text-file. Name it `Car-name_Event-name_v2.18EN.rfcmp` (EN is Endurance Race or whatever the abbreviation for your event is). The v2.18 is only for the Oreca, place there the number you got from the previous step.

Create this file for each car

Next up, clear MAS2 again and click on the 6th icon. After that select `Create Single Cmp Package`

![create the package file](https://davidmoll.net/wp-content/uploads/2021/08/15_57_25_08_2021_Elementor__How_To_Create_An_rfcmp-Mod_Dor_rFactor_31265.png)
![create single Cmp Package](https://davidmoll.net/wp-content/uploads/2021/08/15_56_25_08_2021_rFactor2_Mod_Packager_82399.png)

Now you need to add a new component by clicking on the paper icon in the top right.

### The next step is very important!

Navigate to the folder where all your cars are installed. Select the car you want to create the mod for and copy the name of the folder. For the Oreca it is `Oreca_07_LMP2_2017`. Enter this name the component name

![Car name](https://davidmoll.net/wp-content/uploads/2021/08/16_02_25_08_2021_Vehicles_65061.png)
![Component name](https://davidmoll.net/wp-content/uploads/2021/08/16_02_25_08_2021_Edit_Component_Name_01585.png)

Afte this click on the cabinet icon on the right above the red square and right of the file-dropdown. Navigate to the rfcmp-folder and select the respective file of the car. __Select it but do no press Open yet!__ Instead increment the version in the file name by 1 on the smallest digit. So for example:

Previous | Edited
------------ | -------------
Car-name_Event-name_v2.18EN.rfcmp | Car-name_Event-name_v2.19EN.rfcmp

After that you can open the file.

![Changing file name](https://davidmoll.net/wp-content/uploads/2021/08/16_09_25_08_2021_Select_location_for_component_23173.png)

Now you can edit the Version field. Enter the new version plus the events abbreviation (2.19EN as an example), click the check-mark at “Update from:” and enter the old version next to it (2.18). Select “Vehicle” in the Type-dropdown.

Now click the cabinet-icon the the middle right above the red X. Select the cars .mas file you create in the previous step. After that you can click on “Package” in the bottom row and after that “Install”. The red square should change to green at success.

![Finished Component Package](https://davidmoll.net/wp-content/uploads/2021/08/16_17_25_08_2021_Create_Component_Package_13920.png)

## Finish line

And that’s it, next time you open the game it will automatically download the new mod and you can select the livery when selecting a car. I hope this guide was helpful, if you have any questions or edits you would like to see please hit me up and I will see how I can help.

Have fun racing and remember to always drive save