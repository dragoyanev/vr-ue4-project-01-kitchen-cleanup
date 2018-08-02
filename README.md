# Unreal Engine 4 VR Kitchen Cleanup Project READ ME

This project is part of [Udacity](https://www.udacity.com "Udacity - Be in demand")'s [Unreal Engine 4 VR Nanodegree](https://www.udacity.com) and is based on the template project provided by the course in [GitHub](https://github.com/udacity/Unreal-Intro-Project-Template).

This project makes a game within Unreal Engine 4 for room-scale VR. It is needed to utilize motion controllers for a kitchen-themed interaction game. Spawn messy dishes and get them into the sink as quickly as possible!

## Necessary Controller
 - The project is developed and tested with Oculus Rift

## Necessary Software
- [Epic Games Launcher, Unreal Engine 4.15](https://www.unrealengine.com/en-US/blog)
- [Oculus Home](https://www.oculus.com/setup/)

## Audio Assets
- Original samples downloaded from [freesound.org](https://freesound.org)

## Detailed description
The game experience is lasting 60 seconds before the game is over. Every 10 seconds are spawned additional 10 dirty dishes.

- Player should go over the "Red button" in the scene with one of the controllers meshes to start the game. It have helping text shown in front of the player view . Every time the Red button is pressed the game is restarted
- Plates are spawned from the Left controller current position within the reach of the player, in the kitchen.
- The plates can be grabbed pressing Grip button when the top of the controller mesh (magic wand) is in the plate range. Plate should be moved to the sink area.
- When plates get to the sink, they then "disappear" only if staying there continuously for 2 seconds and are removed from level.
- More plates spawn after a set amount of time 10 seconds, plates spawn in waves. 
- Actor bp_sink_box acts as the sink that "washes" the plates
- After the plate stayed in the sink for 2 seconds it is "clean" and thus is counted towards the score.
- Visually is kept track of how many plates have been washed and how many are dirty.
- When game is started/restarted it ends after 60 seconds despawns all the plates.
- Plates waves left are visible for the player.
- The timer starts on event (StartTimer) casted by overlaping "Red button" in the scene with any of the controllers. The timer is looped and every 10 seconds calls event SpawnRandomPlates. The handle is destroyed when all waves of plates (currently set to 6) passed timer was triggered 6 times.
Timer is created in MyVRPawn.
- For the game experience are used both motion controllers. Plates are grabbed by Grip buttons.
- Audio cue is played when plate clening is finished
- Audio cue is played in loop when the level starts until the timer ends.
