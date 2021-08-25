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
  *Team 1
  * Team1.dds
   *Team1_region.dds
  * Team1.veh
  *Team 2
  * Team2.dds
   *Team2.json
  * Team2.veh
  * Upgrade
    * car1-upgrade.ini
    * car2-upgrade.ini
  * Car 1 MAS
    * car1.mas
  * Car 2 MAS
    * car2.mas
  * rfcmp
    * car1.rfcmp
    * car2.rfcmp
