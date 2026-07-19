# Cameron Fox

Hi! I'm Cameron, I'm a games programmer and recent computer science graduate from the Univeristy of Cambridge. Originally from Barnsley, I now live in Cambridgeshire. I completed an Engineering Internship at Studio Gobo in summer 2025 and I am currently a Graduate Programmer at Frontier Developments. My games, many game-jam entries and my Steam release, Anchor Up, are released under "Orange Flag Studio". I was also the co-founder and co-president of the Cambridge University Game Development Society (CU-Devs), alongside Samuel Shakeshaft. (Updated 19/07/2026)

[Experience](https://cameron-fox.com/#experience)

[Contact and Further Links](https://cameron-fox.com/#links-and-contact)

[Project Portfolio](https://cameron-fox.com/#project-portfolio)

[Cambridge University Game Development Society](https://cameron-fox.com/#cambridge-university-game-development-society)

[Personal](https://cameron-fox.com/#personal)

## Experience

### Professional

| Dates | Role | Company | Location |
| :--- | :--- | :--- | :--- |
| August 2026 - Present | Graduate Programmer | [Frontier Developments](https://www.frontier.co.uk/) | Cambridge |
| June - September 2025 | Intern Engineer | [Studio Gobo](https://www.studiogobo.com/) | Brighton |

### Education
Skipped and self-taught Year 10 in secondary school, therefore completing all exams a year earlier than typical. Attended non-selective state schools.

| Dates | Institution | Qualifications / Program |
| :--- | :--- | :--- |
| July - August 2026 | Peking University Shenzhen Graduate School | School of Electronic and Computer Engineering Funded Research Placement |
| October 2023 - July 2026 | University of Cambridge, Gonville and Caius College | First-Class BA (Hons) in Computer Science |
|September 2021 - July 2023 | Penistone Sixth Form | Four A*s in A-level Physics, Computer Science, Maths, Further Maths | 
| September 2017 - July 2021 | Darton Academy | GCSEs with four 9s, five 8s and 8 in self-taught computer science GCSE sat in Year 9 |

### Teaching

| Dates | Institution | Role |
| :--- | :--- | :--- |
|August 2024| [Linacre Institute](https://linacreinstitute.org/) | Mathematics Teacher | 
|August 2024| [Sutton Trust](https://summerschools.suttontrust.com/university-partners/university-of-cambridge/) | Computer Science Ambassador|
| July 2024 - January 2025 | [Apply Cambridge](https://www.undergraduate.study.cam.ac.uk/find-out-more/widening-participation/apply-cambridge) | Computer Science Mentor |

### Awards

| Award | Description | Institution |
| :--- | :--- | :--- |
|Child's Maths Award | Awarded for highest achieving overall maths results | Penistone Sixth Form |
|Sheffield Hallamshire University Academic Achievement Award | Highest achieving overall A-level results | Penistone Sixth Form |
|Computer Science Award | Highest achieving computer science results | Penistone Sixth Form |

## Links and Contact
- [Itch.io page](https://orange-flag.itch.io/)   
- [YouTube channel - Orange Flag Studio](https://www.youtube.com/@orangeflagstudio7841)
- [LinkedIn](https://www.linkedin.com/in/cameron-fox-970216273/?trk=opento_sprofile_topcard)
- Email: orange.flag.studio28@gmail.com

## Project Portfolio

### Current Projects

#### Machine Learned Cloth Simulation: Generalised File Format [Dissertation Expansion]

Continuing work on my dissertation by creating a generalisable file format for machine learned soft bodies for use in 3D video games.

#### Large Language Model Game Dialogue Research

Seeking to publish work undertaken in my final year on LLM assistance for dialogue tree writers. The work studies the integration of LLMs into writing practises, as opposed to using them to replace writers.

### Game Jams

Since my first game jam in 2019, I have competed in over 20 of them. I love the fast paced nature of going from absolutely nothing to a full game in just a few days. It is fair to say that game jamming is what got me hooked on programming. I intend to continue doing at least one game jam a year to keep the streak going! Some highlighted ones are below.

- [Trade Secrets](https://orange-flag.itch.io/trade-secrets) - Stealth-action / card-trading game with procedurally generated countries [CU-Devs vs Gamma 2/14]
- [Phoenix Fall](https://orange-flag.itch.io/phoenix-fall) - Gliding-descent game with procedurally generated levels [BTP Jam #3 - 152/1023]
- [Prisoners of Conscience](https://orange-flag.itch.io/prisoners-of-conscience) - Stylised stealth game with multiple endings depending on how the player behaves [Wowie Jam 3.0 200/972]

### Cutting Costs: Machine Learned Cloth Simulation For Games
[![Cloth Dissertation Paper](https://github.com/Cameron-Fox-28/Cameron-Fox-28.github.io/blob/main/DifPCA_ClothExample.png?raw=true)](https://www.linkedin.com/posts/cameron-fox-970216273_gamedev-unity-maya-ugcPost-7481929219220963328-QrXI/?utm_source=social_share_send&utm_medium=member_desktop_web&rcm=ACoAAELGBuQBFGwlU9ZYXYzzZzVh37sNZeOoMak)

[Full Dissertation Paper](https://github.com/Cameron-Fox-28/Cameron-Fox-28.github.io/blob/main/Cutting_Costs_Machine_Learned_Cloth_Simulation_For_Games.pdf)

This was my final year dissertation project which scored 70.5%. The project implements an end-to-end solution for training and deploying machine learned soft bodies into Unity using the ['Subspace Neural Physics' (SNP)](https://dl.acm.org/doi/10.1145/3309486.3340245) technique developed by Ubisoft LaForge.

The example implementation demonstrates an interactive cloth simulation with a player controllable sphere. The training data was acquired using an automated solution capturing Maya nCloth data into Alembic files before being converted into the subspace for training. The trained models were stored in a separate virtual environment and could be used to render offline simulations (for quick validation of results) before being exported into the format used by the Unity implementation.

The models were trained to target different PCA basis sizes, which would allow for the quality and detail of the models to be traded with performance. The greater number of bases, the more detailed the soft body would appear.

I implemented both a CPU sided implementation using Unity's Job System and a GPU compute shader model. The compute shader implementation kept the neural network results (calculated using Unity's 'Inference Engine') and subsequent mesh deformation exclusively on the GPU.

A summary of the key results from the project:

- With equivalent solver frequencies of 60, the SNP-GPU-compute-implementation achieved comparable (and consistently 1% higher) global framerates to Unity's own cloth component for up to 32 cloth instances.

- Through a user study, there was no identified loss in believability between the training cloth animations captured in Maya and the results of the trained implementation in Unity.

- The cloth simulation could take place nearly entirely on the GPU, allowing for greater freedom in workload placement. This is not currently possible in Unity's own cloth component or Magica Cloth (the top 3rd party asset). The model could also use Unity's Job System for a CPU sided implementation which showed comparable performance to Unity's component up to PCA-128 for up to 8 instances.

- Iterations (generating the next frame) of the mesh are produced in the realtime implementation at 15X that of the offline Maya nCloth simulation. Coupled with no observed loss in believability, the technique has the potential capability of letting artists create arbitrarily complex physics material interactions in Maya and a comparatively believable version can be placed in game at a fraction of the cost.

### Anchor Up
#### Trailer:
[![Anchor Up Trailer](https://img.youtube.com/vi/aNCixTz0mXI/0.jpg)](https://www.youtube.com/watch?v=aNCixTz0mXI)  
[Anchor Up - Steam Page](https://store.steampowered.com/app/1384000/Anchor_Up/)  
Turn-based strategy puzzle game I independently made (art, code, etc...) in 15 months between April 2020 and August 2021, made in Unity (using C#). Implemented the Steam Cloud required file structure system in the saving of player progress, and the use of Steam Achievements. Responded to feedback received in the [Jonas Plays Your Game](https://www.youtube.com/watch?v=Tjy0-ewKuYk&t=1s) video in which the game was playtestsed, specifically updating the graphics for player movement and adding a realtime tutorial.

### First Person Puzzle Platformer for <ins>Epic Games</ins> - UEFN + Verse Group Project
#### Trailer:
[![Checkpoints Video](https://img.youtube.com/vi/vFUcptDM0K0/0.jpg)](https://www.youtube.com/watch?v=vFUcptDM0K0)  
[Group project demonstration video for showcase](https://www.youtube.com/watch?v=foZVlAiNoqo&list=PLstyePOvf2d1HSBklMXWbdLd_4T2X8pIT&index=4)

[Game page](https://www.fortnite.com/@checkpoints/0653-7115-6439?lang=en-US)

At university, I led a group project where the client was Epic Games' technical director James Golding. The project was to experiment with checkpoints in interesting ways and implement this using UEFN and Verse. I created the game concept, overhauled the UI and wrote a custom inventory system to allow us to have game-specific items, something not currently extensible within the default Fortnite inventory and UI, as well as having an unbounded inventory size. I also handled all manipulation of the system, from collecting new items to handling selection with player input. I also created the state-previewer script for the location and object-reference floppy disks, which was used for displaying, in-world, the stored data of the currently held disk - this was later extended by team mates for the temporal floppy disk. The project brief did not require a fully playable experience, however I felt it was important to create a playable game in order to demonstrate why such checkpoints could be fun! I therefore designed and implemented all playable levels, 3D modelled and textured all custom assets, created any custom 2D assets and handled the publishing process.

### 3rd Person Cover System
#### Dev-log:
[![Cover System Devlog](https://img.youtube.com/vi/_-vrriGN1yU/0.jpg)](https://youtu.be/_-vrriGN1yU)  
Using Unreal Engine 5 and C++, I implemented multi-segment cover rails as well as full wrap-around cover (e.g. moving around a box) with appropriate character rotation per segment. I controlled the cover animations using a blend-space within animation Blueprints, all other logic was wrote in C++. I wrote a custom component to make the creation process for new pieces of cover streamlined, new pieces could be created and dragged into the editor and would work straight away as demonstrated [here](https://www.linkedin.com/feed/update/urn:li:activity:7282817796915298304/). Variable height cover added to demonstrate tagging certain sections of rail.

### DNGN - Gamebridge 2025 Pitching Competition Winner
#### Trailer:
[![DNGN Trailer](https://img.youtube.com/vi/x7JMQEBYFqI/0.jpg)](https://www.youtube.com/watch?v=x7JMQEBYFqI)  
[DNGN - Freshers Fair Build](https://cu-devs.itch.io/dngn-freshers-fair-ver)  
4 player gamepad dungeon crawler. Co-lead alongside Sam Shakeshaft. I designed the Enemy AI system such that enemies could use the same weapons as players and this would affect their behaviour. I also implemented the entire audio system, including the audio that was used, and the major gamelooping features (ensuring the resetting of game state and singletons on death). Learnt to handle Git merges on a larger scale than I had before.

DNGN was also the winner of the [Gamebridge](https://gamebridge.uk/) 2025 pitching competition meaning that the game will receive industry support with a current working plan of being launched in late 2026.

### C++ Particle System  
#### Dev-log:
[![Particle System Video](https://img.youtube.com/vi/LH8dyr6qCl8/0.jpg)](https://www.youtube.com/watch?v=LH8dyr6qCl8)  
I completed the Sumo Digital C++ course using their one-line game engine. I then used the framework to create my own particle system, demonstrated in the video above. This was then reviewed by a developer at Sumo Digital who was able to provide valuable feedback about code efficiency improvements.

### Trade Secrets - Post Jam Expanded
#### Trailer:
[![Trade Secrets Trailer](https://img.youtube.com/vi/eZCSa96XqB4/0.jpg)](https://youtu.be/eZCSa96XqB4)  
[Game Page - Play in Browser](https://orange-flag.itch.io/trade-secrets) 

For the Cambridge University Game Development Society (CU-Devs) vs the University of Hokkadio Game Development Society (Gamma) 48 hour game jam we hosted, the theme was *secrets*. My submission "Trade Secrets" was a stealth-action / card-trading game where the player infiltrates secret-service buildings to collect secrets and then trades these with other countries in order to have certain combinations of secrets which can be used to topple countries. The countries in each playthrough are procedurally generated and the player can face off against a custom set number of them. The levels are also semi-procedural with obstacles, secrets and their contents and the appearance of the room procedurally created from the information of the current country being visited. Some secrets allow players to visit other countries or trade with their leaders - the worth of secrets is also dynamic depending on who the trading-country is. The game placed 2nd in 3 categories including in "overall".

### 3rd Person Ledge-Climbing Character Controller
#### Trailer:
[![3rd Person Controller Video](https://img.youtube.com/vi/JsnFtw4QK7k/0.jpg)](https://www.youtube.com/watch?v=JsnFtw4QK7k)  
Solo project where I created a 3rd person character controller and camera for a stealth game demo in Unity. The USP for the stealth game was the ability for the character to dash through walls, and also dash through enemies to kill them. The ledge climbing also implemented corner transitions and slope climbing.

### Photography Weather App  
#### Demonstration video:
[![3rd Person Controller Video](https://img.youtube.com/vi/3fuzVbWm56s/0.jpg)](https://www.youtube.com/watch?v=3fuzVbWm56s)  
Team project for the Interaction Design course. I implemented custom element animations, filtering-by-condition (e.g. if you wanted to take a rainy photo, it would show you the nearest locations where it is currently raining) and a tab system such that the weather-data pages could easily be swapped between by clicking the add button and then clicking on tabs at the bottom. Used React-Native. Taught me how to code web apps using hooks and events.

### GeoTIFF to 3D Model - Flat Route Planner
#### Demonstration video:
[![Route Planner Video](https://img.youtube.com/vi/OsSs4PIqN9k/0.jpg)](https://www.youtube.com/watch?v=OsSs4PIqN9k)  
Created a GeoTIFF to 3D model generator. I then adapted the A* pathfinding algorithm to find the flattest routes, with a variable max-incline that the pathfinder will then try to adhere to. Taught me how to decode TIFF formatted data and the representation of 3D models at a lower level - something I have learnt much more about at university since.  

### Procedurally Generated Boss Fights
#### Demonstration video:
[![Procedural Boss Fights Video](https://img.youtube.com/vi/PD7mZSkJmu4/0.jpg)](https://www.youtube.com/watch?v=PD7mZSkJmu4)  
Used a delegate function strategy for procedurally generating bosses. Movesets are generated at the start of the fight, each boss starts with a certain number of "points" which it then spends on moves or behaviours to add to its moveset, it also spends them on burst moves (e.g. dash three times in a row) and combinational moves (e.g. throw a bomb and jump). Upcoming moves affect the enemy's behaviour, such that if a ranged move is planned to happen next then the boss will try and create distance from the player.

## Cambridge University Game Development Society

Samuel Shakeshaft and I started the Cambridge University Game Development Society (CU-Devs) in our first term at Cambridge. We ran weekly sessions for developers to meet and work on projects. We also ran speaker events, game jams and a community project which became 'DNGN'. Sam and I pitched DNGN at the Gamebridge student games festival hosted by Anglia Ruskin University in 2025. The project won the competetion and received an assortment of industry support. The project is being taken forward by Sam and Adam Catley to a full release (as of August 2026).

Speakers included [Mark Brown](https://www.youtube.com/channel/UCqJ-Xo29CKyLTjn6z2XwYAw), (Game Maker's Toolkit), [Philip Bielby](https://www.linkedin.com/in/philip-bielby-a3a3416b/) (Jagex, Just Won't Die, Build a Rocket Boy), [George Prosser](https://prosser.io/) (Studio Gobo, Act III) and [James Golding](https://www.linkedin.com/in/james-a-golding/) (Epic Games).

Sam and I also both attended the lecture given by Demis Hassabis on his return visit to Cambridge in 2025. We were also lucky enough to have one of us picked to ask a question on behalf of CU-Devs about the future of AI for video games which can be seen [here](https://youtu.be/hHooQmmzG4k?si=Ojm6hmzHn4L8q5vk&t=3657).

- [Instagram](https://www.instagram.com/cudevs/)
- [Society Page](https://www.cambridgesu.co.uk/organisation/cu-devs/)
- [Cambridge Game Jam 2025](https://camgamejam.com/#about) - Ran in partnership with CUCATs.
- [CU-Devs (University of Cambridge) vs. Gamma (University of Hokkaido) Game Jam](https://itch.io/jam/gamma-vs-cudevs) - Possibly the first UK-Japanese university vs. university game jam.
- [Article about the founding of the society](https://www.cai.cam.ac.uk/news/more-game-caians-set-game-dev-society)

## Personal

### The Nick Drake Bateman Recreation

[![Film Trailer](https://i.ytimg.com/vi/5NdEnjvTdHI/hq720.jpg)](https://www.youtube.com/watch?v=5NdEnjvTdHI)  

In my final year of university, I accidentally left the book I was meant to read at home when making the termly move back to Cambridge. I'd seen somewhere over Christmas that Nick Drake, a late 1960s folk artist I'd listened to over the previous year, had gone to Cambridge so I decided to see if there were any books I could read about him; thankfully, there were! I was very surprised to see how much of a connection to Gonville & Caius College he had. This is the college I attended, but Nick had actually been to Fitzwilliam College. When I found out his first dedicated concert took place in the nearby Bateman Room, which was where I sat my mocks, I thought it would be great to recreate it. Many of the recordings Nick Drake had made in Caius were recorded in Q4 tree court - just a few corridors away from my own N14 - in Robert Kirby's former room. I had not heard of Kirby before, but I had heard his music; I was a keen fan of Tim Hart and Maddy Prior's 'Summer Solstice' album.

I set out contacting Richard Morton Jack (whose biography of Nick I was reading) and the Nick Drake community in search of sheet music. Unfortunately lost, the sheet music was skillfully recreated by Homerton student Lucas Harley and wonderfully played by Homerton College Music Society musicians. I also couldn't believe it when Peter Rice, the man who recorded the original concert in 1968, agreed not only to speak at this event but to record it in that space once again. Once the first night sold out, the waitlist for the event grew to near the venue's capacity. Once announced, the second night sold out within 24 hours.

Robert Kirby's son was also in attendance at the first night, opening the evening with remarks about the collaboration between his father and Nick. Marcus Bicknell, who played flute at the original concert and went on to promote Nick as a live act in the early 70s, also supplied many digitised concert posters and newspaper clippings to be displayed at the event. The Nick Drake estate also donated to the evening.

Through pay-what-you-can ticket sales, the event raised over £1200 for the mental health charity Mind. The events were filmed and a concert video will be released later in 2026. The film for 'The Thoughts of Mary Jane' was played at The Annual Nick Drake Gathering 2026.

Below are a collection of links related to the event.
- [Caius College article announcing the project](https://www.cai.cam.ac.uk/news/caians-homage-nick-drake)
- [Varsity article about the project](https://www.varsity.co.uk/music/31774)
- [Feature in Cambridge Centre for Music Performance Summer Sounds playlist](https://www.cmp.cam.ac.uk/posts/2026/06/30/cambridge-sounds-summer-2026/)
- [Caius College interview with Peter Rice about the original and the recreation](https://www.cai.cam.ac.uk/news/meet-caian-who-recorded-nick-drakes-cambridge-concert-and-its-re-creation-58-years-later)
