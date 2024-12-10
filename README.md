# FGCScoreBoardOBS

Uses localStorage in OBS browser to interact with browser sources. Less hassle of interacting and parsing a JSON/excel/text file. 
Scoreboard for fighting game tournaments, as a html file used for OBS. I do not plan on including 

This will be useful for people who run offline tournaments, and online tournaments too but please note this is more designed and built for offline. 

## How to set up
Note: Tested with OBS 31.0.0-rc1, should theoretically work with most versions of OBS.

1. Add ```panel.html``` as a dock
   1. Docks -> Customer Browser Docks.. -> Add dock name + ```http://absolute/C:/"ENTER THE FILE URL HERE"``` -> Apply
2. Add ```gameOverlay.html``` as a Browser Source
3. Should be good to go from there. (add screenshots for steps)

## Progress
panel and gameOverlay interact now. 
saving records works (just for score at the moment, implementing everything else soon)

## TODO LIST:
- Everything
- Import database/JSON/excel/text
- Wishlist: 
  - 1v1s
  - 2v2s
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
  - Start.gg api implementation