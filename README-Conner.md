# Plunder Party

**Unit Name:** Gameplay Design and Programming

**Student Names:** Conner Vian

**Student IDs:** 2500411

**API Reference Link:** \[URL]

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

Next and likely the most common type of ragdoll is the active ragdoll this type uses a combination moter driven joints and physics to attempt to mimic a spesfic pose or animation instead of going completly limp, this gives the charecter a puppet on strings type effect where they are controlled by the envioment around them but can still move around the stage like something is holding them up while giving physics based reactions the objects around them. These forces pulling and pushing on the ragdoll can be configured and changed to change how the ragdoll reacts around the world they are in going from a basic puppet on strings to a more bouncy spring like ragdoll which can move and hit the ground but will never completly fall. This can be used in combination with inverse kineamatics and other animation tricks to animate the charecter based on the state of the ragdoll and make some movements look cleaner

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

In unreal when you want to call a interface function all you have to do is get the node by typing whatever its name is, grabbing it like any normal node and passing in the target actor in the scene. Now unreal here will do all of those checks in the backend without you the developer needing to do anything extra and the best part is that in the circumstance that the target does not posses the interface, as it is treating this as something similar to an event call rather than a direct function call, the code will just ignore it and keep going without throwing any game breaking errors. Additionally if like in the Figma above your interface method returns something you can just pass that value into a "isValid" macro to see if anything returned and respond appropiately so even in that circumstance there is still a way of being sure you have the data you need when you need it. 

## Implementation *(Approx. 30–40% of word count)*

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



## Testing *(Approx. 10–15% of word count)*

### What testing methods did you use?

* Did you conduct internal testing, peer testing, or user testing?
* What were your key goals in testing?
* What did you observe or learn from testing?
* How did testing influence the final result?

You may include screenshots, graphs, tables, or embedded videos to demonstrate tests and results.

| Tester | Platform | Device Specs           | Test Type      | Bugs Found | Avg. FPS | Severity (1–5) | Repro Steps Provided | Feedback Summary                                                       |
| ------ | -------- | ---------------------- | -------------- | ---------- | -------- | -------------- | -------------------- | ---------------------------------------------------------------------- |
| User A | Chrome   | i7, GTX 1060, 16GB RAM | Internal (Dev) | 3          | 60       | 2, 3, 4        | Yes                  | “Controls are responsive. Minor stutter near large particle emitters.” |
| User B | Firefox  | Ryzen 5, 8GB RAM       | Peer Playtest  | 2          | 58       | 1, 2           | No                   | “Menu system works well, but level loading feels slow.”                |
| User C | Edge     | i5, Intel UHD 620      | External User  | 5          | 45       | 2, 3, 4, 3, 2  | Yes                  | “Performance drops during explosions; some UI overlaps text.”          |
| User D | Chrome   | M1 MacBook Air         | Guided Test    | 1          | 62       | 2              | Yes                  | “Tutorial is clear. Suggested adding a visual checkpoint marker.”      |
| User E | Safari   | iPhone 12 Safari       | Blind Test     | 4          | 50       | 2, 3, 3, 4     | Partial              | “Enjoyed art style. Unclear level goals; needed more on-screen hints.” |

*Figure 4: User Testing Data.*

---

## Critical Reflection *(Approx. 10–15% of word count)*

### What went well?

* What strengths or successes stood out in the final piece?
* Did anything exceed expectations?

### What could be improved or done differently next time?

* Were there things that didn’t work? Why?
* What would you try differently with more time or resources?

---

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


---

## Declared Assets

You must declare any content that was **not entirely created by you**, or was **modified with the aid of AI tools**. This includes:

* Third-party 3D models, audio, textures, or code
* Code snippets from tutorials or forums
* AI-generated or AI-assisted assets (e.g. ChatGPT, GitHub Copilot, DALL·E)

List these clearly, with context where needed.

Example:

> The following assets were created or modified with the use of GPT-4o:
>
> * `Test.cs` – generated structure with manual revision
> * `UIAudioManager.cs` – refactored with Copilot suggestions
> * `DevelopmentJournal.html` – generated layout and headings

---