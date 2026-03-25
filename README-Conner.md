# Plunder Party

**Unit Name:** Gameplay Design and Programming

**Student Names:** Conner Vian

**Student IDs:** 2500411

**API Reference Link:** \[URL]

**Build Link:** \[URL or Embed]

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