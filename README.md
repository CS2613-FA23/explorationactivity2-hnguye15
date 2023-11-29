# Exploration Activity 2
## Package/Library
The program works around JavaScript's Pixi.js, which is a module used specifically for UI and Animations.

## Demonstration
The program builts upon Exploration Activity 1, which was played as an RPG idle incremental game. For those who are unfamiliar with the terms, "idle" means you can leave the game in the background and it plays for you, and "incremental" means the numbers in the game just keep growing larger.

## Purpose
Initially, the program was written as a passion project, but later on expanded as a personal learning experience specific to web application development. It is just a game, and a game gives you enjoyment.

## Samples
NOTE: In order not to spoil the experience, there will be no screenshots for this. Enjoy!

The character first starts off at:
- level 1
- 20 HP
- 5 MP
- 0 experience
- 0 gold

To increase these parameters, you can use the "VENTURE" action to encounter and then kill monsters to earn experience to level up. It is pretty much a typical RPG experience. The main purpose of earning more level is killing things faster. See, each enemy/monster has a specific time needed to kill, but with a higher level you can kill them quicker, thus helping with progression.

This new version of the game removed some redundancy in mechanics (like training) while improving and adding to the main mechanic (HP and MP, real-time progress, button feedback are more responsive!). This version also introduces a log box that automatically logs down specific player actions and events to inform the player of what is happening. It also added a "REST" action in order for the player to restore their health points or mana points when needed (but you have to wait!). Finally, animation for enemies/monsters is added, and it is shown when in combat.

You can notice that in the box to the bottom right of the screen, there are other options like "CHARACTER" and "INVENTORY". These are not yet implemented, will be in the future! You won't be able to do anything with them right now though.

## How to run
Just download the content of this repository (or clone it) in a folder. Then, run start_app.bat. The game will automatically detect your default browser and opens itself accordingly. When you are done with the game, be sure to go to the command terminal opened by the .bat file and press CTR-C to close the server hosting the game (press it again if it does not work the first time). Simple as that!

NOTE: For those who are on MacOS, change your directory into the folder that contains all the files and then run this command in your console: "install -g http-server". Wait for it to finish downloading, then run this command "http-server -c-0 -o" while inside the very same folder. The game should open up correctly.
