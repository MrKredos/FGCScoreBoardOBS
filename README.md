# FGCScoreBoardOBS

Uses localStorage in OBS browser to interact with browser sources. Scoreboard for fighting game tournaments, as a html file used for OBS.

This will be useful for people who run offline tournaments, and online tournaments too but please note this is more designed and built for offline. 

FYI: The panel saves to localStorage, you can read localStorage to then create your own overlays using HTML and CSS. 
Feel free to have a look at my examples for inspiration.

## How to set up
Note: Tested with OBS 31.0.0-rc1, should theoretically work with most versions of OBS.

1. Add ```panel.html``` as a dock
   1. Docks -> Customer Browser Docks.. -> Add dock name + ```http://absolute/C:/"ENTER THE FILE URL HERE"``` -> Apply
2. Add ```gameOverlay.html``` as a Browser Source
3. Should be good to go from there. (add screenshots for steps)

## List of Variable names used in localstorage
```
__Players&Comms__
pName1 to pName4
pScore1 to pScore4
pSponsor1 to pSponsor4
pTwitter1 to pTwitter4
pPronoun1 to pPronoun4
pLosers1 to pLosers4
cName1, cName2
cSponsor1, cSponsor2

__General__
round
game
eName 
eNumber 

__Crew battles__
teamsData
  playerIdCounter
  names
  teamsData
    teamA, teamB
      id
      pName
      pSponsor
      pTwitter
      pPronouns
  
__Unused__
pCharacter1, pCharacter2 //might discontinue this idea, too many games to play around. 
```
## Changelog
```

Progress
v2.9 POST OMEGA 4 
added demo for OMEGA 4 stuff (more like examples, i'll show demos whenever i feel like it (never))

panel.html 
- removed msg, don't really plan on using it any time soon. 
- change some of the JS stuff to be more scalable for multiple players (for 4 players at the moment)
- cleaned up some of the code 

v2.8 
organised the repo a bit more, 
- demos folder for all of my work/examples.
- moved test*.html to css folder where they belong. 

panel.html
- corrected some issues, was only editing p1 and p2, not p3 or p4. 
  - changed some values to get it working. 

css/p5stars.css & p5stars-test.html
- created a background to emulate persona 5 stars background, took a lot of work for probably one of the worst implementations ever lol
  - my implementation is basically, it creates a new star that expands out, and destroys itself after sometime, can adjust values; 
    - frequency = cooldown before creating the next star
    - speed = how fast the stars move
    - you can already imagine the performance issues with this one, 30 stars * maybe 10 stars to emulate the moving sensation * every 0.5 seconds lol.
  - was going to improve on this but i don't think i will be using this in future.
    - i need a better implementation if i plan on continuing this, and i think the solution is either:
      - 1. processing.js -> create something using that wont use as much resources (i already have some sort of idea for this one)
      - 2. after effects and just add it to the website (which I am probably gonna do). 
- do not recommend using, maybe for learning purposes, on what not to do lol. 

v2.7
panel.html (p3&p4 functionality)
- added p3 & p4 toggle 
  - for free for alls/teams
    - for teams, still need to find a way to dictate teams (possible with tick box)
- small QoL changes listed below 
  - toggle buttons change colour when toggled
  - changed named of Swap Players to Swap P1&P2, because there is no way to swap with P3 and P4 atm. 

working on mk world overlay, barebones.
also cleaned up the repo a bit. needs more cleaning

v2.61
panel.html (crew battles QOL): 
- no longer automatically updates
  - added save button for each player.
    - so that changes made are not shared until you want it to, and to save on performance (negligible, but it can add up)

chrom-vs-cfalcon/gameOverlay.html: 
- figured out hacky solution for reading localstorage
  - everytime it detects and update to localstorage, it will destroy (if there is) the previous html, and then re-build the html for the player details. 

v2.6
Add crew battle capabilities and half-tone.css filter for fun or fun (I kinda just ripped off https://leanrada.com/notes/pure-css-halftone/ huge props to them!).
Crewbattle capabilities also added, however they are very barebones and needed to get them shipped in like 3 days. I will continue to work on it however. 

panel.html/crewbattles-test.html (crewbattles-test.html is older version)
- crew battle capabilities
  - basic run down of added stuff
    - toggle crew battles
      - good so that it isn't shown all the time, especially if you're not using crews.
    - add players, remove players buttons
      - will remove for both sides, please keep in mind.
    - auto saving
      - no need for save button   
    - reset all button
      - removes details from localStorage

half-tone.css
- just black and white and only one layer. need to figure out how to use colour (separate layers for each colour).

v2.5 
panel.html
- added "Grab start.gg details" buton
  - save button no longer picks up these details. 
- ui changes
  - twitter box smaller
  - colour on fetch requests
- created halftone filter
  - css/halftone.css
  - coloured and b&w
- folder layout adjusted 
  - cleaner, examples for people who want to play around with some stuff

v2.4 
panel.html
- api reading from start.gg (very barebones, needs to be improved)
  - auto filling, barebones implementation
    - type in exact name and it will pick up pronoun and prefix. you are unable to change pronoun or prefix once adding, something to think about. 
- quality of life changes to panel.html
  - added pronoun usage
  - buttons for deleting players and commentators, separate. 
- examples of usage in om3ga folder and trouble in parradise folders

v2.3 
- game overlay comms functionality 
  - hides itself if no comms
- also now using font-awesome 4, occasionally. 

v2.2: 
- adjusted positioning of buttons
- added losers button + functionality   
  - swap works + delete + save

v2.1:
- panel.html minor QOL changes
  - score buttons for changing scores, opacity = 1. 
    - always shows
  - deleting scores works better now
    - scores reset to 0, round reset to tournament 
  - added grand finals to round tab

v2.0:
- everything works properly
  - lots of changes here dunno if i can list them all but i'll try
    - scores + names + sponsors added for both players
      - swap for players added
    - comms also added
    - created a custom overlay + comms overlay + colour picker
      - you can use these, IDC. however, please don't use the same colour schemes lol, at least change that much 
- dunno what else to say, kinda forgot what i've done already. look at version history if you really wanna check

v1.0:
- panel and gameOverlay interact now. 
- saving records works (just for score at the moment, implementing everything else soon)

```

## TO DO:
- maybe change the variable names to match start.gg? 
- adding the start.gg api key manually
- searching for indiviual players instead of typing manually
- crew battle
- 2v2s for mario kart world (using crew battle). 
- mario kart world 24 player
## WISHLIST: 
- Everything
- ~~Start.gg api implementation NEARLY THERE~~
- ~~1v1s~~
- 2v2s
- Import database/JSON/excel/text
- Challonge API
- Insta replays 
- Display top 8 bracket, or whole bracket
  - Whole bracket sounds a little too complicated, but worth the challenge
- ~~Exhibitions~~
  - ~~Not deathmatches but like team vs team stuff, maybe up to 20 people per team?~~
  - ~~Similar to how Mildsome does his 3S East vs West series (https://www.youtube.com/watch?v=OsRCyU94hxk)~~
  - ~~Local time display (togglable)~~

