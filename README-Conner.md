# Plunder Party

**Unit Name:** Gameplay Design and Programming

**Student Names:** Conner Vian

**Student IDs:** 2500411

[**Build Link**](https://gingerprogrammer.itch.io/plunder-party)

**Video Demonstration Link:** \[URL or Embed]

---

## Project Outline

Our project involved creating a 3D game in unreal engine called Plunder Party with three indivudual minigames fitting the pirate theme.This involed creating three games mainly inspired from party games like gang beasts, mario party and fall guys. The games in question where 
* A charecter brawler where the goal was to knock the other players off the stage (similar to a game like smash bros)
* A collect-athon game where your goal was to collect randomly spawned treasure and have the most points when the timer is up
* A survivor game where the goal was to ensure you were the last player standing as a ship fires cannon balls to knock you off
 
These all working towards keeping to the pirate theme with different things like having a ship circling the player, collecting treasure and other thematic ways of keeping to the pirate theming. The main gameplay loop will be jumping between the 3 minigames amassing score as you go and seeing who has the most score when you are done with the experiance. Along with this a core feature to be shared thoughout the game is the ragdoll charecters akin to something from human fall flat or TABs which give the game a more light hearted and comedic approach though how the ragdolls interact with the world

---

## Research

### Methodology
During my research I intend to look at a combination of infomation on how to create ragdolls in unreal and how OOP techniques work in unreal engine as with this project the nature of how the charecter ragdolls and how a charecter ragdolls is going to be very important for development as the charecter being like this is one core feature that is being kept across all three minigames and also works to define the games style and general feel so getting this right is very important. Additionally with a larger project like this looking into how unreal handles princples like OOP will be very important to ensure scalable code between minigames and just make for easyier development in general thoughout the project. Along with this I will be looking into other UE5 features like local multiplayer as this is also another core of the game as this is going to be a local 4 player party game. Towards this end I'm going to reading and watching relevent resources while looking into similar games and how they do these features like gang beast,TABS and human fall flat to name a few examples.

I am going to attempt to get reviews from groups of people during the game being made to get valuable testing data esspesically since this is made for mutiple players to play at once which means the player experiance being good is vital otherwise people can get bored and just go to something else. I will be approaching this testing with a unguided forward mindset to get a better idea of how a normal person would play my game.

### Sources

### Physics based animation research and Ragdolls

![](https://file.garden/aSY-yx_ZmANpQe1l/PlunderParty/PhysicAnim)
Figma 1 - Excerpt from Ragdoll Physics Wiki Page (Ragdoll physics, 2026)

Thoughout my research I went though the process of looking at many different sources on how ragdolls work and how to make a ragdoll that would be best for the game in question. 

![](https://file.garden/aSY-yx_ZmANpQe1l/PlunderParty/HaloRagdoll)
Figma 2 - Halo (Halo (franchise), 2026) charecter ragdoll

There is a couple of different ragdoll types and they all behave differently from each other and have different pros and cons. First is the passive/traditional ragdoll, where the charecter behaves normally till the charecter dies or the ragdoll is activated and all movement of the charecter switches to its rigid body skeleton reacting purely to gravity and other enviomental forces typically used in sandbox games like Hitman (Hitman (franchise), 2026) and GTA5 (Grand Theft Auto V, 2026). Another type is the Blended/Hybrid approach to ragdolls where a charecter can behave normally in the world but dynamically blend into a ragdoll state as needed for the charecter this prevents the instant snapping to ragdoll giving a better effect than instantly dropping from the envioment around the charecter in the traditional approach this is typically used in more conventional fps games like Halo (Halo (franchise), 2026), as the dynamic shift can make the charecter feel more real. 

![](https://file.garden/aSY-yx_ZmANpQe1l/PlunderParty/TABSRagdoll.gif)
Figma 3 - Tabs (Totally Accurate Battle Simulator, s.d.) Active Ragdoll

Next and likely the most common type of ragdoll is the active ragdoll this type uses a combination moter driven joints and physics to attempt to mimic a specific pose or animation instead of going completly limp, this gives the charecter a puppet on strings type effect where they are controlled by the envioment around them but can still move around the stage like something is holding them up while giving physics based reactions the objects around them. These forces pulling and pushing on the ragdoll can be configured and changed to change how the ragdoll reacts around the world they are in going from a basic puppet on strings to a more bouncy spring like ragdoll which can move and hit the ground but will never completly fall. This can be used in combination with inverse kineamatics and other animation tricks to animate the charecter based on the state of the ragdoll and make some movements look cleaner

![](https://file.garden/aSY-yx_ZmANpQe1l/PlunderParty/PhysicsAnimation.gif)
Figma 4 - Example of Physics based animation in UE5 (Unreal Engine 5, s.d.)

I also looked into the UE5 Physics based animation (Physics Driven Animation in Unreal Engine | Unreal Engine 5.7 Documentation | Epic Developer Community, s.d.) tool to see if that could be used for the project. This tool could be used to give the charecter a hybrid type ragdoll where it would affect the charecters mesh allowing the player to react to the envioment around them and other forces but this effect would only be a visual difference that would get applied against any regular animations the player was playing with a strength value being used to dicate how far the animations should be dicated by physics or the just the normal course of the animation 

Going down this rabbit hole was very useful for the project and learning about ragdolls as a whole as one of the main draws of the game similar to a game like TABS (Totally Accurate Battle Simulator, s.d.) and knowing what types of ragdolls are out there and the techincal infomation around them allowed me to be better informed of what I would end up using on the game created. In the end I went for somewhere between a hybrid ragdoll for general moving around and using of the player and a passive ragdoll for when I wanted to show some real impact when player would get hit off the map in the minigames. This will be done with a combination of unreals physics based animation and normal ragdoll physics on the charecters mesh controlled though blueprints to get the correct effect.

### Modular Unreal Techniques 

While working on unreal for this larger scale project I looked into how to make my project more scalable on unreal and how to make it easyier for other developers to work with my code as with this project I would have another developer working on it along side myself so ensuring the code I made was not only good for me to use but someone else was vital to the success of the project. Towards the goal I did some research into how coding practices like OOP translated into unreal and to my surprise they translated quite well.

![](https://file.garden/aSY-yx_ZmANpQe1l/PlunderParty/BPI_Player)

Figma 5 - BPI_Player interface used in project

![](https://file.garden/aSY-yx_ZmANpQe1l/PlunderParty/interface-result-cs.png)

Figma 6 - Microsoft example of more conventional interface 

Some of this features that unreal engine has include interface intergration which was fairly useful during the projects lifecycle.

Interfaces (Interfaces vs Abstract Classes, s.d.) are best described as a type of contract that can be given to a class that the class must follow to exist. The most conventional utalization of interfaces is to give a common functionality across mutiple classes by making an interface of methods related to whatever functionality its describing and giving this interface to the classes that need this function. An important distinction to made with interfaces is that they don't define what the method actually does only the name and input/output parameters of the method this means that each class that has this interface can have there own code for what that function means when called. This now means that when you call an interface it does not actually know what code is going to be run and just expects that the declaration for that method will do what it needs to do. For a real world example when interaction systems are being made you can either have it so each class in your scene that needs to interact is handled indivualy meaning that you need to check for each class indivualy and write new code for each class being added which can work for small scale projects. However for larger scale projects typcially an interface is used as now instead of doing that you can have a interface called "Interactable" for example and have this contain a method called "Interact" and now each class that needs to be interacted with can have this interface and define what interacting means to that class seperate from the player. Now when the player wants to interact with something it can just grab the object and cast it to the interface if it can and then run that "Interact" method and for additional simplicity the interface can just have the "Interact" func pass the player parameter for the function and then if the player can also be checked and altered inside each class using the interface.  

Interfaces are treated a bit differntly in unreal with some useful inbuilt functionality that makes interfaces more easy and useful to use in unreal than in conventional programming as some of the more difficult parts of using interfaces are abstracted behind unreals systems. One of this being how unreal treats and interface method call. In conventional programming like C# for an example (generalizing for simplicity) to call an interface function you have to first test if the class even has that interface which can be done by running a compination of differnt checks on that class before being able to grab that class as its interface and then run that method, this can sometimes cause problems in those inbetween stages because even if a interface does not care what the class actualy does inside the function, for the code to run the interface refernce does have to be valid meaning in some cases this can throw errors that need to be fixed. However in unreal this part of interfaces is abstracted to a level treating interface function calls almost like if you were to call an event. 

![](https://file.garden/aSY-yx_ZmANpQe1l/PlunderParty/GetPlayer)

Figma 7 - Example of interface method call in UE5

In unreal when you want to call a interface function all you have to do is get the node by typing whatever its name is, grabbing it like any normal node and passing in the target actor in the scene. Now unreal here will do all of those checks in the backend without you the developer needing to do anything extra and the best part is that in the circumstance that the target does not posses the interface, as it is treating this as something similar to an event call rather than a direct function call, the code will just ignore it and keep going without throwing any game breaking errors. Additionally if like in the Figma above your interface method returns something you can just pass that value into a "isValid" macro to see if anything returned and respond appropriately so even in that circumstance there is still a way of being sure you have the data you need when you need it. 

## Implementation

### Process

For the initial planning of the project I consulted my designers with what they wanted out of the three minigames and I worked on converting there requests into the simple core mechanics of what would need to be built for the games. This planning step was useful as it helped inform my step by step process when making the three minigames 

Coming onto the project I had already worked on unreal for a good amount of time and had an intermidate knowledge of the different workings and tools of unreal. Along with this I also have knowledge of the basic ideas of modular programming and how to keep my code clean and organized, this meant that my time did not need to be spent on learning how to invent the wheel rather focusing my attention on some of the new concepts like ragdolling and actually making the game.

I began the project from the base third person game template from unreal engine with the base charecter acting as a base to edit from as I made custom charecter blueprints for the charecters in the game as it already had all the movement code I need inbuilt allowing me to tweak it to get the results I want. Along with this the base level offered quite a good starter place as I began testing systems and mechanics that would be used thoughout the entire project.

![](https://file.garden/aSY-yx_ZmANpQe1l/PlunderParty/PunchABunch.jpg)

Figma 8 - Banner Picture for Punch A Bunch (Punch A Bunch on Steam, s.d.)

![](https://file.garden/aSY-yx_ZmANpQe1l/PlunderParty/PunchABunch.gif)

Figma 9 - Gameplay example of Punch A Bunch (Punch A Bunch on Steam, s.d.)

To start the project, as it was going to be one of the core features of the game,I began working on having a physics based movement sysytem in the game researching different types of ragdolls in games and how they work and differ from each other.After not too much success in my intial testing I remebered seeing a devlog of a indie game,that is now released on steam, on Youtube called Punch a Punch (Punch A Bunch on Steam, s.d.) made by PontyPants(PontyPants, s.d.) which uses the unreal engine physics based animation system which allows keyframed animation to be affected by external
physics.This led me down the rabbit hole of learning how the system works starting the aforementioned research into this system.I also began testing with having the actual character turn into an actual ragdoll during play with varying levels of success at this stage.

![](https://file.garden/aSY-yx_ZmANpQe1l/PlunderParty/RagdollCode01.png)

Figma 10 - Testing of the Ragdolling function on Charecter for seperate componenet

![](https://file.garden/aSY-yx_ZmANpQe1l/PlunderParty/BPCPhysicalAnim.png)

Figma 11 - Picture of BPC_PhysicalAnimation Blueprint

I ended up after following a youtube video on how to do physical animation in unreal engine (Physical Animation: The Ultimate Starter Guide [UE4/UE5], 2022) created a blueprint component for doing physics based animation that I could the tag onto any actor in the game to be able to give them this functionality without having to repeat code. In the tutorial, I learn't how to assign a blend value to the physical animation system allowing to scale how much physics infulence the charecter mesh compared the keyframed animation from 0 to 1 and I decided to create a enum to represent "NoRagdoll,Default,FullRagdoll" with a function made inside of a blueprint function libary to convert the enum value to the relevent value, No ragdoll was 0, Default was 0.2 as it was just enough ragdoll to look nice without it being over the top and Full ragdoll is 1.

![](https://file.garden/aSY-yx_ZmANpQe1l/PlunderParty/BlendEnumToValue.png)

Figma 12 - Picture of aformentioned Enum to Blend Value Function from BPFL_Helper 

![](https://file.garden/aSY-yx_ZmANpQe1l/PlunderParty/LocalMutiplayer.png)

Figma 13 - The code beihind the games Local Mutiplayer

After this as this was also a big part of the project, I made a basic local mutiplayer system following another youtube tutorial/breakdown (Unreal Engine 5 Tutorial -  Local Multiplayer Part 1: Adding Players, 2025) which was fairly easy to do with a inbuilt function in ue5 called "Create Local Player" as shown in the Figma above that allows you to create another player controller in the scene which can automatically connect to a free controller connected to the system, also by putting the player id as -1 it will ensure that the newly created player controller takes the next avaible id in ascending order from one. With this function, you can just use a For Loop and create a local player on evrey loop allowing you to use the end index as a way of defining the player number which here I use as a configurable variable on the game mode. Additionally to give better control over the players being made the GameMode blueprint here also caches these player controllers in an array as they are being created to be easly accesssed whenever they need to be accessed and a event that fires once the players have been created to ensure player contextual actions do not happen till the players actually exist. Small Note player one gets spawned in by default therefore it is  manually added to previously mentioned array manualy before the for loop to create the other players that is also why you can see the player number being minused by one for the end index of the for loop to account for this already summoned player one. I also ended up containing all this logic inside a abstract base game mode called "LocalMutiGameModeBase" containing all the logic for the mutiplayer that is then extended from in all the other game modes created thoughout the game for the other minigames. This was also made in such a way that this blueprints functionality is not context spesfic which means this can and likely will be used in other projects that I will make that need this functionality. 

![](https://file.garden/aSY-yx_ZmANpQe1l/PlunderParty/PunchAction01.png)

Figma 14 - Brawler Charecter Punching Code with Montage

![](https://file.garden/aSY-yx_ZmANpQe1l/PlunderParty/PunchSphereDrawing.png)

Figma 15 - Logic for Making Collision Sphere Around Punching Hand

From here I began properly working on the first minigame now the prequizit functions have been made and as this game was a smash bros like experiance where the challenge was staying on a platform as the other players attempt the knock you off the platform, I made a system for creating punch impulse/pushing when one player hits another also having it tied to the animation the player is playing. This was done by having a sphere trace circle created around the hand the player is attacking with during the period that the montage of the attack animation is playing to track when/if the players hand collides with another player. This trace also has additional logic added to be able to generate a impulse direction based on the direction the hand was moving when it contacted with the player to be able to push the hit player in a direction more indictive of the momentum of what they were getting hit by. This was done by after evrey trace it would track if it hit something or not. If it had not hit something the current location of the hand is cached in a "PreviousSphereLocation" variable until it does contact the player where the current location of the contacting hand is compared to the previous sphere direction to get the vector unit direction of the hit that is then inserted into a "S_HitInfo" struct which is then sent to a "OnPlayerHit" event to be used to compute the players hit reaction

![](https://file.garden/aSY-yx_ZmANpQe1l/PlunderParty/OnPlayerHit.png)

Figma 16 - Event Calling with relvent data OnPlayerHit

![](https://file.garden/aSY-yx_ZmANpQe1l/PlunderParty/PlayerHit.png)

Figma 17 - Player Hit Event

Now once the player is hit first it increases a value called down percentage, this percentage acting as a way of insentavising aggressive behaviour in players as the higher the percentage the more the player gets knocked back and at max percentage its essentially a KO for the player being hit. This value will go down after a time of not being hit. Then a branch is used to check how the player should respond to this hit by checking if the down percentage is at max or not. If the percentage is not max a combination of things are done to move the player. These being in order:

* The Capsule Component is set to simulate physics 
* Then an calculate impulse vector is applied to the the capsule collider 
* A two tick delay to allow the capsule to be affected by the impulse
* Closing the loop the capsule is set back to not simulate physics

![](https://file.garden/aSY-yx_ZmANpQe1l/PlunderParty/CalcImpulse.png)

Figma 18 - Code behind how the punch impulse is calculated

This all working to move the player when being hit, it should be noted the capsule is set to lock the postion so it stays straight up when being hit so after the hit the player will not be on a diagonal.

![](https://file.garden/aSY-yx_ZmANpQe1l/PlunderParty/FullRagdollStrech.png)

Figma 19 - Image of Testing KO Launch

Now if the players down percentage is max this should full ragdoll launch the player as a type of KO. This is done by first setting the charecter to full ragdoll making them a active ragdoll fully limb and then appling a massive impulse directly to the now limb charecter mesh. Both of thse outputs call a on down power changed event once their function is over to allow the down power to update based on the change at the start of this event.

![](https://file.garden/aSY-yx_ZmANpQe1l/PlunderParty/DeathTracor.png)

Figma 20 - Image of Kill Box Code

![](https://file.garden/aSY-yx_ZmANpQe1l/PlunderParty/KillBox.png)

Figma 21 - Debug of Kill Box (Exagerated for effect)

After this I worked on having a way to actually eliminate the players when they leave the map bounds by creating a kill box that could delete the player when it leaves the bounds of the map and also ensures that it doesnt full kill the player when the game has not started. Additionally due to how the game treats the player it had be ensured that it checked if the player had left via its mesh not its capsule collider otherwise it could cause elminations when the player was still in bounds. This was done by first using a cast to validate if whatever has left the range of the collider was a mesh, using the pure version of the cast as I only need the boolean.

![](https://file.garden/aSY-yx_ZmANpQe1l/PlunderParty/BPI_Player)

Figma 22 - BPI_Player interface used as seen in (Figma 5)

![](https://file.garden/aSY-yx_ZmANpQe1l/PlunderParty/BPI_GameMode.png)

Figma 23 - BPI_GameMode interface used

![](https://file.garden/aSY-yx_ZmANpQe1l/PlunderParty/GetPlayerImp.png)

Figma 24 - Implementation of GetPlayer From Player interface

![](https://file.garden/aSY-yx_ZmANpQe1l/PlunderParty/HasGameStarted.png)

Figma 25 - Implementation of HasGameStarted From Gamemode interface

After this checking at the same time a player actor had also left the collider using the "GetPlayer" function on the "BPI Player" interface which does that returning the player actor the interface is on if any. Due to the mentioned mechanics on interfaces prior, we run a "IsValid" on the returned player to verify that we have actually got a player charecter. Then a safty check is ran to ensure this player is actually being controlled and using the "HasGameStarted" method attached to a interface attached to the gamemode. Then if all of these conditions are true it destroys the player actor, importantly not destroying the player controller in case that players needs to be able to do something for any miriad of reasons. If game has not started it resets the player to the starting position bringing them back to the platform

![](https://file.garden/aSY-yx_ZmANpQe1l/PlunderParty/Mario_Party_4_Cheep_Cheep_Sweep.gif)

Figma 26 - Gameplay of inspiration of Game 2

Then as for this project I was not tasking with doing the code around the HUD I moved onto creating the mechanics for the second minigame, this game being the pickupathon game, where you had to collect coins and put them into a chest similar to the cheep cheep sweep game from the mario party games. The player with the most at the end wins.  

![](https://file.garden/aSY-yx_ZmANpQe1l/PlunderParty/BPI_Interactable.png)

Figma 27 - Interact Function in interface

![](https://file.garden/aSY-yx_ZmANpQe1l/PlunderParty/InteractingFunction.png)

Figma 28 - Interaction Function in Blueprint Component

This began with making a modular component based interaction system in unreal using a combination of a interactor component and interactable interface to allow for easy repeatable and scalable creation of this system. For sake of simplicity I used a sphere trace to facilate the interaction, using a custom one I made which behaves the exact same but has a debug feature to see the sphere, then after checking if it hit anything it attempts to cast that result to the interacble interface and using that reference it runs its interact method passing the player actor as a input. After this in both circumstances a boolean is returned to show if anything happened and then interface refernce is also returned in case the actor running the method needs to cache the reference for whatever reason.

![](https://file.garden/aSY-yx_ZmANpQe1l/PlunderParty/InteractOnItem.png)

Figma 29 - Interact method on BP_Item

Now on the item that is being interacted with this code above is ran trying to set the item on the interactor as itself using another interface refernce that will be discussed in a moment and then if it has been given to the interactor it destroys its self.

![](https://file.garden/aSY-yx_ZmANpQe1l/PlunderParty/HeldVar.png)
![](https://file.garden/aSY-yx_ZmANpQe1l/PlunderParty/GetItem.png)
![](https://file.garden/aSY-yx_ZmANpQe1l/PlunderParty/SetItem.png)
![](https://file.garden/aSY-yx_ZmANpQe1l/PlunderParty/HoldingItem.png)
![](https://file.garden/aSY-yx_ZmANpQe1l/PlunderParty/ClearItem.png)

Figma 30 - All Function declarations from BPI_ItemHoldable interface on Player and Held Item Variable Soft Ref

The "TrySetItem" works by taking in a BP_Item reference and first using another function to check that the player is not currently holding an item terminating the function if the player is, this is why the name is prefaced with Try, but if the player is not holding an item it does a combination of a couple things to both logically give the player the item and visually. The logical element is setting the Held item variable to the item thats trying to be picked up and then the visual element is setting a static mesh in the players hands to the mesh of the item being picked up.

![](https://file.garden/aSY-yx_ZmANpQe1l/PlunderParty/InteractItemBox.png)

Figma 31 - Item Box Version of interact function

Now to ensure we can actually put the item inside of one of the boxes, the boxes also have there own implementation of interaction interface with a bit more going on that the base items. So in order:

* First the Player Controller is casted to
* The Player controller ID is compared against the ID that the box listens to 
* The Interacter parameter is casted to the BPI_Itemholdable interface
* The Item on the interactor is grabbed checking if it has any item using the "TryGetItem"
* If check passes true it adds that items data to the boxes array of items
* The orginal item is cleared from the ItemHoldable

![](https://file.garden/aSY-yx_ZmANpQe1l/PlunderParty/MinigameTwoStartTimer.png)

Figma 32 - Timer for Minigame two on GameStart

After this I needed to create an end game condition with a time in this minigames game mode. To create the game timer for this minigame I used the "SetTimerByEvent" Function tied to the end game event with a configurable amount of time in minutes. This timer is non looping and the reference is cached for later use before the game start boolean is set true initating many of the game active mechanics on other scripts. Then when the game is over it compares the length of the the HeldItems array on all item boxes in the scene and awards the win(or tie in some circumstances) to the player/s with the most items in there equivelenet box.

## New Approaches

This project was the first time I was tasked with working in team with mutiple people for a unreal game so this was a new experiance working in collaberation and keeping TABS on evreyone in my team and it came with positves and negitives. For one it allowed me to focus on what I do best as now I had other people who could do work towards their personal talents(modelling,sound design,etc) and i could focus on mine. However as team work typically goes one weak link can bring down an entire project so ensuring that evreyone was on the same page and expecially that I also kept evreyone updated with what I was doing was definatly a new experiance that I have learnt from for projects after this.

## User Testing 

When it came to user testing I learnt a lot about how to make a game that could be tested by others, as I found when it came to user testing it was quite difficult to do this as at certain points the game was more of a collection of parts which are good on their own but did not realy make a good whole meaning that users could not easyly test the game and resulting in them not being able to give amazing feedback which in the future I will definitely work on doing better.

However this is not say I got zero feedback and the feedback I got at differnt intervals did help the make the game better thoughout development. Some of the feedback being:

* The load times between levels in the Menu
* The game felt too snappy 
* The players could somehow skip past the kill box

These being all problems that could be rectafied with a bit of debugging and some balencing of values. For example to improve the game feeling too snappy, values in places like the player movement were adjusted to fix for this issue.

However the main thing we got out of testing was the advice to just in general in the early stages of development to work on features and work towards the goal of having that user playable MVP as early as possible becasue it cant be understated how important user testing is in evrey stage of a project expecially the early stages

## Instruction to Install / Run

To run my project:

Go to the itch.io page for this game using this [**Link**](https://gingerprogrammer.itch.io/plunder-party)

Follow the steps outlined on the itch page

## Reflection 

### Research Effectiveness

The research I did in combination with my designers, unlike the [first project](https://github.com/GingerNinjaProgramming/HorrorThing) I had done in unreal was farily efficient as it very much helped me create the systems I wanted to create and learn about the different options I had when making the mechanics early on. This allowing me to better informed when I went from the theoretical to the more pratical stages of game development. This includes as mentioned before the extensive research I did into different ragdolls in games and how they behaved/worked and which kind of ragdolls I wanted in my game.

### Positive anaylisis

On my postive reflection, this project general code structure, at least in my opinion, was well structured and modular allowing for easy project scalablity if needed and also allowing for transferable mechanics between minigames and even between this game and future games that I may create. As a big goal of all code I write is to make it as reuseable as possible to prevent having to redo simple mechanics in future projects and just in general speed up my personal workflow, even eventually taking a collection of tools made into this project and morphing these into my own plugin.

### Negitive anaylisis

On my negitive anaylisis of this project it could of done with more geneal polish thoughout and more work on certain features to make them feel easyier to use for the player. Along with this as this was one of my first times working in a larger team for a project there was defiently some growing pains to do with that and expecially with my other developer more delegation would be important as I belive this could of allowed me to focus on the priorly mentioned polish and ensured that the mechanics I did make were as perfect as they ever could be with the extra time that delegation would of provided

### Next Time

Next time, I'm going to try and work on letting go of some of the responsibity onto my other capable developers in my project to allow me more time on the features that I am working on and not have to worrie about missing out on anything. Along with this I want to be able to learn how to make systems with more finer polishing behind them which just comes down to doing more research on the things I want to make and the systems unreal provides.

### New Intrests 

As far as what is now guiding my intrests into future projects I will make thoughout my life, I want to work more on creating complex repeatable behaviours that I can have inside of my own personal components and libarys that I can use across other projects and even in the future possibly publish for other people to use as I find my self creating my own personal soltions to problems that bug me and in the circumstance that someone is also having these problems, I would love to be the person to create that solution to allow them to work of the things that intrest them while I make the tools that intrest me, as no problem has only even happened to one person.

## Declared Asset

Version Control: **Git / Github**

IDE: **Blueprints / UE Visual Scripting**

Engine: **Unreal Engine 5.6.1**

AI Used:

* Chatgpt - Debugging / Code Questions
* Unreal Doc AI - Code Questions

## Credits && Sources

‘Last Spurt’ - Umamusume: Cinderella Gray Unofficial OST - https://www.youtube.com/watch?v=ik93qlSSs2k

**All Models and Other Music/Sounds Created by Designers working on project**


## Bibliography

Ragdoll physics (2026) In: Wikipedia. At: https://en.wikipedia.org/w/index.php?title=Ragdoll_physics&oldid=1342851877 (Accessed  25/03/2026).

Hitman (franchise) (2026) In: Wikipedia. At: https://en.wikipedia.org/w/index.php?title=Hitman_(franchise)&oldid=1344432523 (Accessed  25/03/2026).

Grand Theft Auto V (2026) In: Wikipedia. At: https://en.wikipedia.org/w/index.php?title=Grand_Theft_Auto_V&oldid=1344896479 (Accessed  25/03/2026).

Halo (franchise) (2026) In: Wikipedia. At: https://en.wikipedia.org/w/index.php?title=Halo_(franchise)&oldid=1343051722 (Accessed  25/03/2026).

Totally Accurate Battle Simulator (s.d.) At: https://landfall.se/totally-accurate-battle-simulator (Accessed  25/03/2026).

Physics Driven Animation in Unreal Engine | Unreal Engine 5.7 Documentation | Epic Developer Community (s.d.) At: https://dev.epicgames.com/documentation/en-us/unreal-engine/physics-driven-animation-in-unreal-engine (Accessed  25/03/2026).

Unreal Engine 5 (s.d.) At: https://www.unrealengine.com/en-US/unreal-engine-5 (Accessed  25/03/2026).

Interfaces vs Abstract Classes (s.d.) At: https://www.geeksforgeeks.org/videos/interfaces-vs-abstract-classes/ (Accessed  09/04/2026).

Punch A Bunch on Steam (s.d.) At: https://store.steampowered.com/app/1512590/Punch_A_Bunch/ (Accessed  07/02/2026).

PontyPants (s.d.) At: https://www.youtube.com/@Pontypants (Accessed  13/04/2026).

Physical Animation: The Ultimate Starter Guide [UE4/UE5] (2022) Directed by PrismaticaDev. At: https://www.youtube.com/watch?v=46NfgXlnCzM (Accessed  13/04/2026).

Unreal Engine 5 Tutorial -  Local Multiplayer Part 1: Adding Players (2025) Directed by Ryan Laley. At: https://www.youtube.com/watch?v=gB0pXsJ6LQg (Accessed  13/04/2026).
