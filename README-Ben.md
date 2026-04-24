# \Plunder Party

**Unit Name:** Gameplay Design and Programming

**Student Name:** Benjamin Sibley

**Student ID:** 2502747

[**Build Link:**] (https://gingerprogrammer.itch.io/plunder-party)

**Video Demonstrations:**

<video controls src="https://file.garden/ZhvFhTnnzDVjn5ib/PlunderParty/DeckBrawlDemo.mp4" title=""></video>

<video controls src="https://file.garden/ZhvFhTnnzDVjn5ib/PlunderParty/ScrambledBootyDemo.mp4" title=""></video>

<video controls src="https://file.garden/ZhvFhTnnzDVjn5ib/PlunderParty/CannonballPanicDemo.mp4" title=""></video>

---

## Project Outline

We were tasked with creating a 3D multiplayer party game themed around pirates with the game "Plunder Party" that contained 3 unique minigames, we decided to create the following:

- A Top Down Brawler style minigame where the players compete to be the last standing by attacking eachother and knocking eachother off of the map  
- A Collection Based minigame where the players must collect treasure and then take it to their respective chest to store it to gain points, with the winning player being the one with the most points at the end of a timer.  
- A Survival Based minigame where players are on an island being fired at by cannonballs shot from a rotating ship and must dodge them, with the last player standing being the winner.  

Due to its nature as a party game it was decided to create a more lighthearted style of game focusing on comedy, this was highlighted with ragdoll-style characters being left behind on player death, similar to games such as Totally Accurate Battle Simulator. The game maintains its pirate theming through the aesthetic design of all 3 minigames, and their general premises, battling, collecting treasure, and dodging cannonballs.

---

## Research 


One important aspect of our game is the inclusion of ragdoll characters, for this we were inspired by popular games including Gang Beasts and Totally Accurate Battle Simulator

*Figure 1: Trailer Footage of Totally Accurate Battle Simulator*

![](https://file.garden/ZhvFhTnnzDVjn5ib/PlunderParty/tabitha%20gif.gif)

*Figure 2: Trailer Footage of Gang Beasts*

![](https://file.garden/ZhvFhTnnzDVjn5ib/PlunderParty/gang%20breasts.gif)

These ragdoll games are unique as their overexaggerated physics increase the comedic potential in the games which makes them work better as lighthearted party games.

I was tasked with the development of the entirety of the third minigame, Cannonball Panic, for inspiration, I looked at the Mario Party 1 Minigame, Bombs Away, which has a very similar premise to our game.

[Video of the Mario Party 1 Minigame, Bombs Away](https://www.youtube.com/watch?v=9uXEjvIiM2E)

One notable differences between this and our minigame is that the Mario Party 1 Minigame has a stationary ship, while our minigame will require a rotating cannon around the island that the player's must dodge on. In order to implement this into the game, I chose to use a spline in order to create the path that the cannon follows, for this I used a video tutorial to setup the spline and make the cannon follow it.

*Figure 1: A spline in the Cannonball Panic minigame*  
![](https://file.garden/ZhvFhTnnzDVjn5ib/PlunderParty/boatspline.png)



I also used a video tutorial for assistance when implementing rebinding controls. We chose to implement rebinding controls as an essential aspect of any game in the modern era of games.

---

## Implementation

### What was your development process and how did decisions evolve?

The BP_OrbitingBoat blueprint will trigger the Move Object function when play begins.

![](https://file.garden/ZhvFhTnnzDVjn5ib/PlunderParty/Screenshot%202026-04-24%20004046.png)

The Move Object function will set the play rate of the timeline T_Move to the Time to Complete divided by 1, this ensures that the timeline T_Move will play for the time to complete, by default 5 seconds.

![](https://file.garden/ZhvFhTnnzDVjn5ib/PlunderParty/image.png)

A reference to the spline is taken and used to get the length of the spline.
![](https://file.garden/ZhvFhTnnzDVjn5ib/PlunderParty/im2age.png)

the spline length is used as the Alpha input for a Lerp, which takes the move track of the timeline T_Move as the ending, and 0 as the beginning.
![](https://file.garden/ZhvFhTnnzDVjn5ib/PlunderParty/aaa.png)

This Lerp is used to get the location and rotation of the distance of the cannon along the spline. 
![](https://file.garden/ZhvFhTnnzDVjn5ib/PlunderParty/afa.png)

Then, on the timeline T_Move's update, the Actor Location and Rotation is set to the distance along the spline
![](https://file.garden/ZhvFhTnnzDVjn5ib/PlunderParty/chungus.png)

This creates the effect of the orbiting around the island.

In order to have the cannonballs fire, I used the TIck Event with a delay of 2 seconds to trigger the Fire Event.

![](https://file.garden/ZhvFhTnnzDVjn5ib/PlunderParty/aaaaaaaa.png)

The Fire Event will first get all actors of the player class, then place them into an array, it will then take a random element from that array and set it as the targetted player.
![](https://file.garden/ZhvFhTnnzDVjn5ib/PlunderParty/awajfbaev.png)

Then, it gets the transformation of the targetted player, as well as the cannon's location and suggests a projectile velocity using the two locations, starting at the cannon.

![](https://file.garden/ZhvFhTnnzDVjn5ib/PlunderParty/nobody%20will%20read%20this%20but%20i%20love%20yuri.png)

The Cannonball is then spawned, following this velocity

![](https://file.garden/ZhvFhTnnzDVjn5ib/PlunderParty/spawncannonynyntnn.png)

Rebinding controls were implemented, as control rebinding is universal in modern games, and would be the expectation of the audience.

The WP_InputSlot Widget handles the visuals and button inputs. 

![](https://file.garden/ZhvFhTnnzDVjn5ib/PlunderParty/good%20image.png)

When a button is pressed, it checks to ensure it is valid and then triggers the On Key Button event, setting the Active Input Slot for use in the WP_Rebind widget.

![](https://file.garden/ZhvFhTnnzDVjn5ib/PlunderParty/i%20miss%20firefly.png)

WP_Rebind, on its construction, triggers a custom function “Add Input Rows”.

![](https://file.garden/ZhvFhTnnzDVjn5ib/PlunderParty/heavenly%20restriction%3A%20divine%20lock%20in%20of%20destruction.png)

The Add Input Rows function creates a list of controls and their current key by getting the user settings of the owning player, and using it to find the player's mappings, before placing this into an array.

![](https://file.garden/ZhvFhTnnzDVjn5ib/PlunderParty/one1.png)

For each key in the array, a WP_InputSlot widget is created, this allows for the addition of as many keys as needed to the options.

![](https://file.garden/ZhvFhTnnzDVjn5ib/PlunderParty/on2.png)

The Text both for the Input Action and the button are then set on the WP_InputSlot widget.

![](https://file.garden/ZhvFhTnnzDVjn5ib/PlunderParty/o3.png)

---

### New Approaches

When developing this project, I newly learnt how to collaborate and work in a team within Unreal Engine, which was unique as rather than creating a game alone I was delegated specific tasks to do. Additionally I had to make use of projectile physics which will likely be useful in any future projects. Timelines and Splines were also new to me, and I can also see being useful in the future, especially for making objects follow a set path.

## User Testing 

User playtesting was enlightening with some useful feedback both towards the earlier and later stages of the project, which greatly assisted with the fixing of bugs.

One notable bug that was fixed was the players not dying when they should and simply returning to the play area. This was caused by the player characters respawning by mistake and was quickly fixed.

User Feedback was mostly positive overall, but mild imperfections like slow loading times were able to be addressed and fixed thanks to user testing.

---

## Critical Reflection

### What went well?

Overall I am pleased with my contribution to the project, as I successfully was able to create the entirety of the Cannonball Panic minigame and had meaningful contributions to the UI and Menus.

### What could be improved or done differently next time?

 I feel that in a future team project I would be able to effectively contribute more than I did in this one, this issue was further complicated in this instance by my late entry to this group, around 2 or 3 weeks in.

---

## Bibliography

Mario Party (1988)  
Totally Accurate Battle Simulator on Steam (s.d.) At: https://store.steampowered.com/app/508440/Totally_Accurate_Battle_Simulator/ (Accessed  24/04/2026).  
Gang Beasts (s.d.) At: https://gangbeasts.game (Accessed  24/04/2026).  
How To Make An Object Follow A Spline Path - Unreal Engine 5 Tutorial (2025) Directed by Matt Aspland. At: https://www.youtube.com/watch?v=fm0_W6YV_8k (Accessed  23/04/2026).  
Enhanced Input Key Rebinding (2025) Directed by Alamar’s Dev Domain. At: https://www.youtube.com/watch?v=Iy5JwCYx1fE (Accessed  24/04/2026).  
Unreal Engine 5.6 Documentation | Unreal Engine 5.6 Documentation | Epic Developer Community (s.d.) At: https://dev.epicgames.com/documentation/unreal-engine/unreal-engine-5-5-documentation (Accessed  24/04/2026).

---

## Declared Assets

Version Control: **Git / Github**
IDE: **Blueprints / UE Visual Scripting**
Engine: **Unreal Engine 5.6.1**

## Credits && Sources

‘Last Spurt’ - Umamusume: Cinderella Gray Unofficial OST - https://www.youtube.com/watch?v=ik93qlSSs2k

**All Models and Other Music/Sounds Created by Designers working on project**