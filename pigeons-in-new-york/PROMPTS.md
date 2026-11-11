# All prompts: Pigeons in New York

Every prompt I wrote to the AI (Claude), in order and copied exactly (typos included). Under each one: what we did and how it turned out.

✅ = worked · ❌ = didn't work, tried again · 🔍 = only checked, nothing changed

[▶ Play the game](https://marie-6.github.io/hello-world/week7-8/) · [Process record](PROCESS.md)

---

## Part 1: Finding the idea (Oct 27–28)

**1.**
> okay, i need to create a one-button game. do you have any ideas about what game to make?

The AI suggested 5 ideas (Lighthouse Keeper, Bloom, Echo…). ❌ Not what I wanted.

**2.**
> do you know flappy bird? i think that is a great one- button game, can  you think of anything fun and interesting and new about one-button game

The AI explained why Flappy Bird works and gave 5 new twists. ❌ Still felt like old games.

**3.**
> i recall a music game called"dancing line", that only need you to tap, right

The AI explained Dancing Line and gave music game ideas.

**4.**
> but that's not interesting?

The AI gave stranger ideas. ❌ Still not new enough.

**5.**
> i mean interesting games that looks new and not like other games we mentioned before, new game. let's maybe start with a topic?

We started from a **topic** instead of other games. ✅ This gave me my own idea.

**6.**
> maybe we can create a game called"pigeons in newyork", which is a game similar to the crossing road game. but only press one button for the pigeon to stop and hold the button for pigeon to fly. and pigeons should avoid people and cars. how about htis

**My idea.** The AI planned it: the pigeon walks by itself, tap to stop, hold to fly, and a Wings bar so you can't fly forever. ✅

---

## Part 2: Building the game (Oct 28)

**7.**
> yes! pls make sure the pigeon's movement is funny like in the real life they move their necks and walks so funny

The AI built the game. The pigeon's head stays still, then jerks forward like a real pigeon. It also waddles, looks around, pecks pizza and says "coo". ✅

**8.**
> but i after pressing tap, i dont know how long the pigeon's gonna stop or when will it start walking again?

A tap used to stop the pigeon for a hidden 0.9 seconds. Now **tap to stop, tap again to walk**, with a sign above the pigeon while it waits. ✅

**9.**
> and maybe you can change the mode to " easy- middle- and hard"

Added **Easy, Medium, Hard**. They change car speed, gaps, lanes, buses, Wings and people. ❌ Easy was still too hard (see 10).

**10.**
> the easy mode is still to hard

Easy got much easier: cars at half speed, bigger gaps, **no buses**, longer flying, fewer people. ✅

**11.**
> change tap to pree "space

All the words now say **"Press Space"** and **"Hold Space"**. ✅

**12.**
> should i add like 3 lives for the pigeons? or i die so fast

The AI suggested 5 lives for Easy, 3 for Medium and 1 for Hard.

**13.**
> yeah i i think 3 lives in every mode is good enough

**My choice: 3 lives in every mode.** When hit, the pigeon says "Ouch!", gets dizzy stars and blinks for 2 seconds. ✅

**14.**
> there's just 3 maps? can you add more maps? like washington square park? add more maps and maybe each one is different and dont repeat them in one game

**12 neighborhoods**, including Washington Square Park. Each has its own look and traffic, and none repeats in one game. ✅

**15.**
> but now if i eat soo many pizzas, i will never die?

Each extra life now costs more pizza: 10, then 20 more, then 30 more… ✅

**16.**
> there are so many people in medium mode right now, can you maybe delete some?

New people now came less often. ❌ It didn't really help (see 18).

**17.** *(with a screenshot of the start page)*
> it seems like so many words in introduction, can you make it easier for people to understand the game?

The start page now has only the goal, the 2 controls, 3 short tips and the mode buttons. ✅

**18.**
> still a lot of people on the pavement, maybe delete some? can you find the balance of avoiding the cars and the people?

Found the real problem: people kept coming with **no limit**. Now each sidewalk has a fixed number of people, so cars are the main danger. ✅

**19.**
> sometimes there's no way out of the traffic with cars but no space to cross?

Bug: the gaps between cars got too small later in the game. Now every gap is big enough to walk through, and wide streets have a **safe island** in the middle. ✅

---

## Part 3: Putting it on GitHub (Oct 28 – Nov 1)

**20.**
> yes add it into fungames, also create week 7 in hello-world  and put this in too

Added the game to **fun-games** and **hello-world/week7**. ✅

**21.** *(with a screenshot of the assignment)*
> 检查是否有符合这些要求，以及提交的格式和钥匙有符合吗（不要修改游戏，只是检查）
>
> *(English: check if it meets these requirements, and if the submission format and keys are right. Don't change the game, only check.)*

🔍 Missing: a `sketch.js` file, and the README didn't say which game I started from or which control is automated. Also found: extra inputs (Enter, ↑, mouse) and no way to win.

**22.**
> okay, fix the missing parts and no way to win but only lose, keep 3and4, dont change that

Moved the code into `sketch.js` and added the missing README parts. **My choice:** keep the extra inputs and keep "only lose". ✅

**23.**
> did you push it up?

🔍 Yes, it's on GitHub.

---

## Part 4: Fixing and polishing (Nov 2)

**24.**
> i notice that cars are covering each other sometimes, fix that and make sure cars don't Overlap

Bug: a new car only checked the last car added. Now it checks **every car in its lane** before it appears. A test showed overlaps went from about 120,000 frames to 0. ✅

**25.** *(with a screenshot)*
> the cars still overlap?

🔍 The screenshot was the **old page**, because GitHub updated at the same minute. A refresh (`Cmd + Shift + R`) showed the fix.

**26.**
> did you update the links in github?

🔍 Yes, both links had the fix.

**27.**
> okay, but the cars are running in parallel. can you change them to different speed?

Each **lane** on a street now has its own speed. Cars in the same lane share a speed, so they can't drive into each other. ✅

**28.** *(with a screenshot)*
> the fountains are overlapping, fix that. make sure nothing is overlapping

Decorations only go where there's space and always leave room to walk. People walk around fountains, pizza and each other. ✅

**29.**
> when the pigeon is hit, maybe add a status of being hit. perseve the shinning and dizzy part.

Added a big hit effect: spinning, X eyes, screen shaking, red flash. ❌ I didn't like it (see 30).

**30.**
> change it to the last version, i dont like this version of being hit

Went back to the version before. ✅

**31.**
> still add a stop or just being hit when it's being hit, perserve the dizzy and shining

A simpler version: when hit, the pigeon **stops for a moment**, then blinks with dizzy stars. ✅

**32.**
> okay, when changing mode at the beginning. maybe can add a start, so people can hestitate when thinking about which mode to begin

Clicking a mode now only selects it. A **Start** button (or Space) begins the game. ✅

**33.** *(with 2 screenshots)*
> why when hit by a bus and died, why it seems different from getting quashed by a car? make sure it's all like image#7

There were 2 death looks: flat (car) and lying on its back (everything else). Now **every death is flat**. ✅

---

## Part 5: Writing it down (Nov 3)

**34.** *(with a screenshot of the process-record assignment)*
> according to this， include all of the request and keep tracking : decisions+ Mechanism+ errors. make sure you made clear about why making this decision and how you change it, does it work or have to try another way, how do i describe the propmt.

Wrote `PROCESS.md` with every decision, how it works and every error, plus a test page (`probes/traffic-overlap.html`). ❌ Too complicated (see 35).

**35.**
> sometimes too complecated, maybe i'l give you an example:
> Which choice did i  make?  explain the rules in the begining page, and add start for people to hesitate whether start playing this mode or not, so they dont begin the game while only pressing the mode/ buttons(space)to walk and stop and status of holding space (flying); add 3 lives for more time playing; the way the pigeon move its neck; the car speed and number of cars; buses only appears in medium and hard; car/fountains overlapping; car runs in parallel...

Rewrote `PROCESS.md` in my style: short lines under **"Which choices did I make?"** ✅

**36.**
> okay, output a file about what we do and keep all the prompt and make it clear

This file. ✅
