# FGCScoreBoardOBS

Uses localStorage in OBS browser to interact with browser sources. ~~Less hassle of interacting and parsing a JSON/excel/text file.~~ edit: yeah nah I've got no clue what I'm saying.
Scoreboard for fighting game tournaments, as a html file used for OBS.

This will be useful for people who run offline tournaments, and online tournaments too but please note this is more designed and built for offline. 

## How to set up
Note: Tested with OBS 31.0.0-rc1, should theoretically work with most versions of OBS.

1. Add ```panel.html``` as a dock
   1. Docks -> Customer Browser Docks.. -> Add dock name + ```http://absolute/C:/"ENTER THE FILE URL HERE"``` -> Apply
2. Add ```gameOverlay.html``` as a Browser Source
3. Should be good to go from there. (add screenshots for steps)

## List of Variable names used in localstorage
- pName1
- pName2
- pScore1
- pScore2
- pSponsor1
- pSponsor2
- pSponsor1
- pSponsor2
- pCharacter1 //UNUSED FOR NOW
- pCharacter2 //UNUSED FOR NOW
- pLosers1
- pLosers2
- cName1
- cName2
- cSponsor1
- cSponsor2
- round
- game
- eName // event name
- eNumber // event interation number 


## Progress
v2.4 
panel.html
- api reading from start.gg (very barebones, needs to be improved)
  - auto filling, barebones implementation
    - type in exact name and it will pick up pronoun and prefix. you are unable to change pronoun or prefix once adding, something to think about. 
- quality of life changes to panel.html
  - added pronoun usage
  - buttons for deleting players and commentators, separate. 
- examples of usage in om3ga folder and trouble in parradise folders

TO DO:
- maybe change the variable names to match start.gg? 
- adding the start.gg api key manually
- searching for indiviual players instead of typing manually


v2.3 
- game overlay comms functionality 
  - hides itself if no comms
- also now using font-awesome 4, occasionally. 

v2.2: 
- adjusted positioning of buttons
- added losers button + functionality   
  - swap works + delete + save

need to do:
- socials tag (twitter)
- swap comms 
- bracket link

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

## WISHLIST:
- Everything
- Import database/JSON/excel/text
- Wishlist: 
  - ~~1v1s~~
  - Display top 8 bracket, or whole bracket
    - Whole bracket sounds a little too complicated, but worth the challenge
  - Docker will change depending on the scene shown. 
  - Exhibitions
    - Not deathmatches but like team vs team stuff, maybe up to 20 people per team?
      - Deathmatches can use the 1v1s page
    - Similar to how Mildsome does his 3S East vs West series (https://www.youtube.com/watch?v=OsRCyU94hxk) 
    - Local time display (togglable) 
  - Insta replays 
  - Challonge api implementation 
  - Start.gg api implementation NEARLY THERE
  - 2v2s (can probably do without)