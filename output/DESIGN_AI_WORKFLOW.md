# Design AI Workflow
Document how you used AI to do the design work — not just to write prose:

## 1. AI Tools used
*Which AI tool(s) and why?*

For this test I used mostly chat GPT, I also used Claude to verify some information. Chat GPT is the AI I was thought to use in my last job, and it works great for me, but I have no problem in trying out a more specialized AI.

## 2. Prompts used
*3–5 concrete prompts you used and what they produced (diagnosis, stat proposals, sim extensions, edge-case hunting, GDD drafting).*

**1. GDD Drafting:**  Im going to make the GDD on a new game mechanic that adds a layer of complexity and decision making to the game, its a triangle system (rock paper scissors) where elemental damage exists,
   there will be 3 types of elements that influence combat, fire, ice and poison, fire is effective against ice, ice against poison and poison against fire, the GDD will be split down in the following tabs,
   Overview, Why / Design Goals, Changes to combat, changes to units and changes to enemies, balance considerations, feedback/UI, and finally edge cases 

     This prompt produced a base for the GDD, but after doing this I always read the whole thing and modified it, 
     I adjusted the document to my needs, rebalancing, adding and removing stuff, to kickstart a GDD this is a prompt that I often
     use, it's easier to modify a text than to start from zero, I also used a couple of "refine this: " every time I wrote a new
     paragraph to improve the readability of my writing.

**2. Balancing Sheet:** I need you to create a google sheet table with the following information, (ignore the elemental affinities and debuffs) have each unit in separate lines with their stats,
have the Turns to kill, hit chance, and the win % against each of the enemies in the game

    This prompt generated a .xlsx file with the requested TTK, hit% and win%, the problem is that the values in each cells
    were pre-calculated by the AI meaning that any changes done to the spreadsheet would result in no changes to the values, so
    I had to manually modify the spreadsheet to add the formulas so that I could start balancing the different units.

**3. Getting the Simulation to Run (lol):** How can I run this Python Program (pasted code)

    I'm not a programmer so I had some issues making the simulation run, So I used chatGPT to instruct me on how to run the program, which worked 
    great and allowed me to continue my work on the assignment, I also asked how the simulation was calculating the win%, which surprised me a little bit since
    it is being calculated based on fights between the unit against all other units and not against the actual enemies of the game.
        

## 3. Mistakes by AI
*One moment where the AI was wrong or misleading and how you caught it. (A model will happily propose "balanced" numbers that fail in the sim — show that you verify against evidence, not the model's confidence.)*

- When I requested the **Win% formula against enemies**, It gave me a really long formula that when I tried using the results were nothing like previous
  results the AI had previously calculated, and upon giving it to claude AI it recommended not using the formula and leaving the win% calculations for the Simulation

## 4. Ways to Scale the development
*How you'd scale this: balancing 50+ units across multiple games per quarter with an AI-assisted pipeline.*

- I like to use spreadsheets to balance complex game systems, by creating the base spreadsheet with all of the formulas balancing 50+ units it's just a matter of adding their stats to the sheet
and fine-tuning until we find the desired balance, AI could be a great help in the initial development of this spreadsheet, refining formulas, and transfering long data into the sheets
