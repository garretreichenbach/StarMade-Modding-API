# Setup and Installation
## Prerequisites
This documentation assumes you have basic Java knowledge and are familiar with the StarMade game. If you are not familiar with Java, you can find many resources online to help you learn.
It should also be noted that this documentation is not a guide for StarMade itself, but rather a guide for modding the game. For help with the game itself, please refer to the [StarMade Wiki](https://starmadepedia.net/wiki/StarMade_Wiki).
## IDE Setup
You can use any IDE of choice, but we recommend using IntelliJ IDEA. It is free and has many features that make modding easier. You can download it [here](https://www.jetbrains.com/idea/download/) (scroll down until you see the Community Edition download).
## Mod Template
While not required, there is a Mod Template repository available to help you get started in modding StarMade. It contains a starting point for your mod, as well as some utilities to help you along the way. You can find it [here](https://github.com/garretreichenbach/ModTemplate).
### Mod Template Setup
Once you have cloned the Mod Template repository, you can open it in your IDE. To set up the project, edit the `gradle.properties` file to match your mod's information. You can also edit the `build.gradle` file to change the mod's dependencies and other settings:
```gradle
# Done to increase the memory available to gradle.
org.gradle.jvmargs=-Xmx4G

# Change this to match your StarMade install. Trailing / required. Can also use StarMade-Gradle's publish folder.
# Can be overridden using "-Pstarmade_root=my/starmade/root" for automated build purposes.
starmade_root=C:/Program Files (x86)/Steam/steamapps/common/StarMade/StarMade/

# The version of your mod.
mod_version=1.0.0

# The name of your mod. Can contain anything a normal file can contain in its name.
mod_name=ModTemplate

# Should be a domain you own, in reverse. If you do not have a domain, the common practice is to use your name (alias or real) instead.
mod_org_id=username.modname

# Can be your name, or the server/dev team that works on the mod.
mod_org=Example Org

# Should be a link to your Github or StarMadeDock page.
mod_url=https://github.com/garretreichenbach/ModTemplate
```
By default, the `build.gradle` configuration is set to export the mod to your `StarMade/mods` folder.
### Running Your Mod
To run your mod, create a new Jar application configuration in IntelliJ IDEA. Set the Jar path to the path of the StarMade.jar, and the directory to the folder containing StarMade.jar. You can directly launch into the game by adding the following program arguments:
```shell
-force -uplink localhost 4242 9999
```
- `-force` is used to force the game to run without the launcher.
- `-uplink localhost 4242` is used to connect to a local server running on port 4242.
- `9999` is the SMD ID of your mod. Since you haven't uploaded your mod to SMD yet, you can use any number here as long as it matches the one in your mod's `mod.json` file.
Before you run your mod, you should also edit your `mod.json` file to match your mod's information:
```json
{
	"name": "ModTemplate",
	"author": "Username",
	"description": "Template for making StarMade mods.",
	"version": "1.0.0",
	"starmade_version": "0.203.164",
	"client_mod": false,
	"server_mod": false,
	"main_class": "username.modtemplate.ModTemplate",
	"smd_resource_id": 9999,
	"dependencies": [
		-1
	],
	"core_mod": false,
	"requires_class_resize": false,
	"hard_load_all_classes": false
}
```