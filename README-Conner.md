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

Going down this rabbit hole was very useful for the project and learning about ragdolls as a whole as one of the main draws of the game similar to a game like TABS (Totally Accurate Battle Simulator, s.d.) and knowing what types of ragdolls are out there and the techincal infomation around them allowed me to be better informed of what I would end up using on the game created. In the end I went for somewhere between a hybrid ragdoll for general moving around and using of the player and a passive ragdoll for when I wanted to show some real impact when player would get hit off the map in the minigames. This will be done with a combination of unreals physics based animation and normal ragdoll physics on the charecters mesh controlled though blueprints to get the correct effect

### Modular Unreal Techniques 

While working on unreal for this larger scale project I looked into how to make my project more scalable on unreal and how to make it easyier for other developers to work with my code as with this project I would have another developer working on it along side myself so ensuring the code I made was not only good for me to use but someone else was vital to the success of the project. Towards the goal I did some research into how coding practices like OOP translated into unreal and to my surprise they translated quite well.

![](https://file.garden/aSY-yx_ZmANpQe1l/PlunderParty/BPI_Player)

Figma 5 - BPI_Player interface used in project

![](https://file.garden/aSY-yx_ZmANpQe1l/PlunderParty/interface-result-cs.png)

Figma 6 - Microsoft example of more conventional interface 

Some of this features that unreal engine has include interface intergration which was fairly useful during the projects lifecycle.

Interfaces (Interfaces vs Abstract Classes, s.d.) are best described as a type of contract that can be given to a class that the class must follow to exist. The most conventional utalization of interfaces is to give a common functionality across mutiple classes by making an interface of methods related to whatever functionality its describing and giving this interface to the classes that need this function. An important distinction to made with interfaces is that they don't define what the method actually does only the name and input/output parameters of the method this means that each class that has this interface can have there own code for what that function means when called. This now means that when you call an interface it does not actually know what code is going to be run and just expects that the declaration for that method will do what it needs to do. For a real world example when interaction systems are being made you can either have it so each class in your scene that needs to interact is handled indivualy meaning that you need to check for each class indivualy and write new code for each class being added which can work for small scale projects. However for larger scale projects typcially an interface is used as now instead of doing that you can have a interface called "Interactable" for example and have this contain a method called "Interact" and now each class that needs to be interacted with can have this interface and define what interacting means to that class seperate from the player. Now when the player wants to interact with something it can just grab the object and cast it to the interface if it can and then run that "Interact" method and for additional simplicity the interface can just have the "Interact" func pass the player parameter for the function and then if the player can also be checked and altered inside each class using the interface.  

expecially due to how unreal has some useful inbuilt functionality that makes interfaces more easy and useful to use in unreal than in conventional programming as some of the more difficult parts of using interfaces are abstracted behind unreals systems. One of this being how unreal treats and interface method call. In conventional programming like C# for an example (generalizing for simplicity) to call an interface function you have to first test if the class even has that interface which can be done by running a compination of differnt checks on that class before being able to grab that class as its interface and then run that method, this can sometimes cause problems in those inbetween stages because even if a interface does not care what the class actualy does inside the function, for the code to run the interface refernce does have to be valid meaning in some cases this can throw errors that need to be fixed. However in unreal this part of interfaces is abstracted to a level treating interface function calls almost like if you were to call an event. 

![](https://file.garden/aSY-yx_ZmANpQe1l/PlunderParty/GetPlayer)

Figma 7 - Example of interface method call in UE5

In unreal when you want to call a interface function all you have to do is get the node by typing whatever its name is, grabbing it like any normal node and passing in the target actor in the scene. Now unreal here will do all of those checks in the backend without you the developer needing to do anything extra and the best part is that in the circumstance that the target does not posses the interface, as it is treating this as something similar to an event call rather than a direct function call, the code will just ignore it and keep going without throwing any game breaking errors. Additionally if like in the Figma above your interface method returns something you can just pass that value into a "isValid" macro to see if anything returned and respond appropiately so even in that circumstance there is still a way of being sure you have the data you need when you need it. 

## Implementation *(Approx. 30–40% of word count)*

### What was your development process and how did decisions evolve?

Describe your technical and creative approach, including:

* Planning, ideation, and iteration
* Feedback received and how it was integrated
* New tools, workflows, or systems explored

#### Example Code Snippet

```csharp
using UnityEngine;

public class HelloWorld : MonoBehaviour 
{
    public void Start() 
    {
        Debug.Log("Hello World!");
    }
}
```

*Figure 2: Example code snippet using Unity's `Start()` method.*

#### Example Image

![Example](https://beforesandafters.com/wp-content/uploads/2021/05/Welcome-to-Unreal-Engine-5-Early-Access-11-16-screenshot.png)
*Figure 3: Unreal packaging menu interface.*

### What creative or technical methods did you try?

Were any methods unfamiliar or experimental? Did they succeed? Did they change your approach?

### Did you experience any technical challenges?

How did you address problems, bugs, or limitations?

---

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