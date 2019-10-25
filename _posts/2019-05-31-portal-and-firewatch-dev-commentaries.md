---
layout: post
title:  "Developer Commentaries: Portal and Firewatch"
# date:   2019-10-22 00:18:23 +0700
categories: [design]
---

This post is for those that played Portal or Firewatch, and want to see a reference of what was said in their developer commentaries. 

All rights belong to the game devs : )

`Portal`

Portal image rendering: using frame buffer and  extensive buffer to work with antialiasing and not using too much video memory to handle recursive view through several portals
At most 9 portals, inexpensive but works. Copy and paste the clone image??
Portal Physics and Rendering: static collision, dynamic collision - clone the object and strictly control  

Comprised Visual Design: round, surface, sharp
Playtesting puzzle-solving, training
Momentum Concept ： flinging - gravity jump + rocket out from another
Classic game design problem: forcing players to lookup using a moving platform
Playtesting player’s bad habits: eg. not looking through portal leading directly to DOOM, force them to look through using a blocked balcony
Association: player associating button with block, so introduce another type of push-button
Adding ticking sound q the player to act - shoot a portal through the open door 

Player training doesn’t always stick, have a level that reintroduces the idea of flinging
Solve the puzzle using as few portals as possible -  add the concept to post game challenge map

The trouble with door and box: portal box, left with player trapped in the room with button - > box supply tool to ensure 
Allow ninja solution - one that bypasses part of the puzzle if it requires more skill than solving it traditionally


`Firewatch`

[GDC talk on the dialogue system](https://www.youtube.com/watch?v=wj-2vbiyHnI)

Playmaker Unity Scripting Plugin

Structures:
The blackboard model defines three main components:
blackboard - a structured global memory containing objects from the solution space
knowledge sources - specialized modules with their own representation
control component - selects, configures and executes modules.[2]

Write in Twine
You don’t have to read dialogue to understand who Henry is and his relationship with his wife because YOU made the choice that brought him to where he is today. 

Interactive Music: 
When you reach a certain point, it sends a note to sth, then it waits for the next appropriate note to transition. So it sounds like the music gets sad at exactly the same rate as your life does. 

In and Out of Look Out tower:
Blueprints from real-world, change the stairs to be outside
Questions how does Henry survive, where does he get water

Firewatch:
Making a game about the most boring job ever,
What do they actually do? To populate objects inside of the tower
As the game goes on, the state of the lookout changes. Henry is a slob. 

Cache Box:
Grey boxing the world: should it be on a cliff, a secret? Or a warm place that player can spend time on 
The locks and password: Prototype detailed object interactions 

Dynamic Map:
The map was one of the last things made, the upside of that
The system used to create dialogue is the same system that checks what’s there and not there.
So based on the dialogue choice, you name the places and write it down on the map

Continuous Streaming World: On graphics and performance programming
Canyon as obvious occlusion
Move through small rocks to occlude line of sight
It’s like a small puzzle game to figure of the line of sight and because it is a not linear story experience, you have to take into account reverse line of sight


Complexities of the teen interaction: 
What you should do in-game is to build predictable ironclad AI systems that react to inputs
They have spaghetti code on the backend and a flimsy state machine with a bunch of if this if that
Still PTSD about bug report of how a player can break the game
The result is believable as there are so many things you could do 
Girls should react to you throwing boombox into the lake, but also reacts to you putting it down

Caves and their lighting:
One of the hardest thing to light in games are areas that are half indoor half outdoor.
Caused a lot of problems in terms of the logic gating of the environment switches. How the place is lit determine the time of the day?
The method they use is image-based lighting: all the objects trees and walls just look out to the sky to see what their lighting should be. So in the cave, they have to create a fake sky for everything inside that is pure black for all the objects in the cave so the lighting would be appropriately dark
When the player enters the cave from the outside and then going back out, everything has to seem natural 

Branching dialogue: “Creep”
The infectiousness of language. We are all non-participatory sponges, weird like that. 
In-game you can do that because it is player-driven and is passive. But in books, it could make the author sounds intentional. 

Directing player tension: 
TeenLoop.unity
This game can actually feel intense and cinematic, everything comes alive

Firewatch’s Day Structure:
The idea comes from Dallas Buyers Club when it cut to Day 1: the gut-punch of tension and what that implies. It also helps to tell a linear story in the open-world setting. 

Hawk’s Reed - a surprise reveal
Innocuous looking cabin on the outside but when you open the door, it is burnt out +  a gust of wind
Overhearing Deliah’s conversation: you can choose to call her out

Firewatch’s visual:
Switching from over the top Hollywood jazz AAA scope to ambient secondary motion national park
The haze and smoke is emitted by Henry’s body and leaving behind the trail; A group of emitters surrounding the tower, if you get really close, you could make it out


Cardboard Single Use Camera:
Connects to the story you experience at the end of the credit

Environmental Breadcrumbs:
Challenge: giving the player an objective when they don’t know where to go
Guide the player through first telephone popes and then beer bottles, call in D to ask, the thin plume of smoke… All of these tools
A box of beer to justify how much beer can be left on the trails by the teens
Mirroring the problems in playtesting when players get lost, eventually, if you don’t ask D and don’t see the smoke then D will call you and hint the smoke. 

Climbing and Navigating Obstacles:
Realize what game you are making, not athletic platforming. So a lot of these end up being in game design terms characterization -> force you to see that Henry is a slub slightly heavier person instead of a ninja edgy person
Also use mantle to break vista, line of sight so you see the creep. 
In the cave, use camera animation to hide a teleport of the path. After a while, the player doesn’t have to climb the mantle too many times. 

Dynamic “Time of the Day” System: 
Player needs to be able to control time, fog, 
Baking data, save everything in-memory data structure and then use it in real-time 
Solution: a fully dynamic system, the fog adapts to the color change, the sun direction, shadow everything is rendered every frame, no information is stored. 
The sky is a shader that blends a bunch of gradience together, to mimic the process of painting in photoshop. With controls and variables like brightness to make sure the sky behaves
The platform system allows artists to test and knowing what it looks like now is close to what we are going to ship

On top of the canyon: way too much game to draw

Ropes, climbing physics:
Ropes have to be physically stimulated, it can’t be a predetermined animation. Took a ton iteration. In the end, I basically had to make Henry’s hand a gravity well. Whenever his hand is on the rope, grab the nearest parts of the rope. Take over left-hand right hand and belt as bones. And reskin the rope every frame to match up perfectly. 

Atmosphere: How to paint color in the 3D world
Using one-dimensional texture, imagine an image of color from left to right, it is the color closest to the player to the color in the distance. In this way, you were able to paint the world. 
Also used in film this technique, but in film sometimes you use hundreds of these strips to paint the entire scene. 

[Color Grading - Unity asset store Amplify Color](https://assetstore.unity.com/packages/vfx/shaders/fullscreen-camera-effects/amplify-color-1894)

Designing and building Henry:
Louie CK as model
Set early on, most important is his hands, the shape is very important. Most expressive,  give animator the thing to work with 

D’s brain:
Lots of heavy state management going on
We look at how long have you been talking to D, how much life stuff has she told you
You don’t want D to go “so… girlfriend” when you are about to discover a mystery like the wire. So we pace the world out and placed cubes trigger all over the world. Every time you enter one, the game asks itself: how long have you been talking to D; How much has D told you about D? What does D know to be true about Julia 
A clean state machine- I can physically pace the game by placing these triggers… Spread these apart, delete that one, but that one over here.

The mid-game “Montage” structure:
A passage of shorter days. Convey the passage of time without spending much of player’s time
Inspirations: cinematics, sports montage, game-Thirty Flights of Loving: story told through hards cuts, series out of chronological order
Combined with the day structure. The second act of the game 

Creating the “Knock out” moment by the game:
Rare fully take over cutscene that is fully animated; 
From behind, along with the broken rope some really punchy action pieces that I got to animate 
Creating score/audio: footsteps creeping from behind, audio panning from left to right, fist Indiana Jone punch 
Compromise between player explosivity and making sure the story is told
Lead to many design uncertainty


The surprising complexity of interaction:
We’ve never asked you to do anything, like an adventure game, use an object on an object. 
It is bad when the game design is subservient to the story. Classic adventure trope: there is something important behind the gate, but you have to go somewhere else to retrieve something and then get in...
Use object on the fence, the gate, the rock, the stick. If break, need to…

Controlled Burn:
The world is made of tiles in a way, to swap in and out the tiles. 

Backtracking, shifting tone:
Medicine wheel as a landmark
Player’s walked here before, how do we keep this place fresh. The lighting, the feel of this place needs to be different so it feels like a new area. Even the sun in a different direction would make space seem like totally different.
The obvious solution is to let the player go in the opposite direction. 

Maintaining scale in level design: 
Hard to tell how big the tree is until you put a model under it

Keeping player and Henry on the same page:
Ended Day76 with “Oh shit” on an ambiguous panic. 
Challenge here is that it is a first-person game that skips time. Your motivation as a player is continuous throughout the game. 
We have to write D to bridge the gap is a concrete example of how the to keep player going
Another big challenge is how to sync player intention with the character’s intention

Cottonwood Creek:
We have to move it back the last 10 weeks of the runway. Using cache box and doing magician shell game swap.

The New Radio: You don’t have to pick it up
There is really no way to constrain the player to go to a certain place except putting infinite walls. The entire research center has to be bifurcated into having the radio or not having the radio
It is hard to logically program it.
The way the branching dialogue works in a game like this is not to choose your adventure and go to a different chapter. The game is going line by line, looking at hundreds of lines and playing the truest one. So a lot of lines are shared across having or not having the new radio. It is jumping between.
It affects music, writing. How do we as designer read your intent: whether you are just doing the I want to check out every place exhaust thing or do you intent to skip the radio. 
It is lots of guesswork, If this then that and not that, that’s what we think the player wants to do and we need to support that. Hopefully, we can do it better. 

Our baffling process: 
Lots of creative solutions to not hard gate everywhere  Gating in Level Design
Because games like Firewatch are designed around ideas and concepts often times as opposed to systems and hard rules. It is easy to forget the decisions you made, and you agonize over the perfect solutions you kind of have for days until you finally just let it go and move on and come up with something else. 

Sound design: 
Started off with most library sound, too big punchy and fully sound effects for this game. (We call it a gamey sound design which is a little bit larger than life. Sometimes you need that for feedback when it’s called for.)
 Ended up with 95% original
This game is about human-scale drama and ambiguity. Also very naturalistic with how the wilderness is presented. 
Get my backpack and record the fence live, every crank and rustle. Going through hundreds of them and find the matching one to the animation.

Animating First Person Character: 
From a third-person Unity editor perspective. Henry has got spider bones, where you could stretch his shoulder, really far away from his torso. 
Earlier, I was looking at gifs of how Crisis does first-person stuff. Almost any animation in the game if you look at it from the outside, would completely destroy the immersion. 
My thoughts: 
Animation: grabbing an object, swift feels good
Right mouse zoom in, swift no dizzy, extreme, actually enlarge shit
Turning Spigot: Water faucet animation turn it on then off so he doesn’t run out of the water but shows that he has access to water and won’t die

Debate with how much of it is a 70s conspiracy, or a story with no single shred of proof.  the team hyped ourselves too much
Maybe we could have pulled back a little bit on all fronts as you are observing by now. 

Building props and set dressing
Manmade, spooky, ambiguous
Just scientific standard stuff used reference from 80s equipment

The bugout bag from GQ magazine, evidence board at the lookout, wave receiver from Far Cry 2 for diamonds, coming at the drunk line from different angles



