# Plunder Party

**Unit Name:** Gameplay Design and Programming

**Student Names:** Conner Vian

**Student IDs:** 2500411

**API Reference Link:** \[URL]

**Build Link:** \[URL or Embed]

**Video Demonstration Link:** \[URL or Embed]

---

## Project Outline

Our project involved creating a 3D game in unreal engine called plunder party with three indivudual minigames fitting the pirate theme.This involed creating three games mainly inspired from party games like gang beasts, mario party and fall guys. The games in question where 
* A charecter brawler where the goal was to knock the other players off the stage (similar to a game like smash bros)
* A collect-athon game where your goal was to collect randomly spawned treasure and have the most points when the timer is up
* A survivor game where the goal was to ensure you were the last player standing as a ship fires cannon balls to knock you off
 
These all working towards keeping to the pirate theme with different things like having a ship circling the player, collecting treasure and other thematic ways of keeping to the pirate theming. The main gameplay loop will be jumping between the 3 minigames amassing score as you go and seeing who has the most score when you are done with the experiance. Along with this a core feature to be shared thoughout the game is the ragdoll charecters akin to something from human fall flat or TABs which give the game a more light hearted and comedic approach though how the ragdolls interact with the world

---

## Research

### Methodology
During my research I intend to look at a combination of infomation on how to create ragdolls in unreal and how OOP techniques work in unreal engine as with this project the nature of how the charecter ragdolls and how a charecter ragdolls is going to be very important for development as the charecter being like this is one core feature that is being kept across all three minigames and also works to define the games style and general feel so getting this right is very important. Additionally with a larger project like this looking into how unreal handles princples like OOP will be very important to ensure scalable code between minigames and just make for easyier development in general thoughout the project. Along with this I will be looking into other UE5 features like local multiplayer as this is also another core of the game as this is going to be a local 4 player party game. Towards this end I'm going to reading and watching relevent resources while looking into similar games and how they do these features like gang beast,TABS and human fall flat to name a few examples.

I am going to attempt to get reviews from groups of people during the game being made to get valuable testing data esspesically since this is made for mutiple players to play at once which means the player experiance being good is vital otherwise people can get bored and just go to something else. I will be approaching this testing with a unguided forward mindset to get a better idea of how a normal person would play my game.

#### Sources

For each source, provide:

1. An **opening paragraph** describing the source's creator/publisher, reputation, and relevance.
2. A **bullet list** of what you analysed or learned from it.
3. A **closing paragraph** evaluating its usefulness or limitations.

You may include both **academic resources** and **industry examples** (e.g. documentation, games, developer talks). You are encouraged to include plenty of images, videos and diagrams.

> You should have at least 1 game source as inspiration, 1 documentation/tutorial source and 1 academic source at a minimum.

---

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

Please use [UCA's Harvard Referencing Format](https://mylibrary.uca.ac.uk/referencing) for all citations.

Example:

> Rollings, A. and Adams, E. (2003) *Andrew Rollings and Ernest Adams on Game Design*. New Riders Publishing.

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

## Tips for Success

* Use plenty of **images, code snippets, drawn diagrams, tables and embedded media** to support your writing.
* Use **inline citations** for everything that influenced your work, including software and games. Include as many **hyperlinks** as possible for easier navigation to external sources.
* Reference **documentation, tutorials**, and **games** just like academic sources.
* Word count is a guideline – ±10% is allowed.
* You are allowed to use AI tools, but you **must declare** them under *Declared Assets*.