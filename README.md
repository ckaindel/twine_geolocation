This sample code provides minimum functionality to use geolocation on mobile devices in Twine/Sugarcube. Currently it only works on Android devices.

Just import the Twee file into Twine. The structure is quite simple and can be kept for most projects. Only the stages need to be modified, and their names and coordinates entered into the *$markers* object.

The appearance of the story is standard Sugarcube, only the UI bar is removed.

Structure:
- **Story Javascript** holds custom functions, mainly for map display using the Leaflet library. They are called in the "Karte"(map) passage.
- **StoryInit**: In this passage all the variables are initialised. The stages of the scavenger hunt are stored in the *$markers* object. It holds the coordinates as an array and the target passage. *$stages* is set to 0 in **StoryInit** and advances with every stage completed.\*$punkte_temp* is the maximum number of points for a single stage. *$punkte* is the total point count.
- **Karte** (map): This passage shows the map with the current position (walking person icon) and the target position (blue marker). The map is updated every 5 seconds. When the player is in range of the target position, currently 30m, a popup link to the target passage appears.
- **Stages**: There are 3 stages with dummy quiz questions using methods provided by the Sugarcube Story Format. Events at the stages are handled by standard Twine code. Additional stages can easily be created as Twine passages. Their names and coordinates then need to be added to the *$stages* object in the StoryInit passage.\The bottom paragraph is the same for most stages and links to the "Falsch" or "Weiter" passages, depending on the answers to the quiz. Only the bottom paragraph of the final stage links to "Ende" instead of "Weiter".
- **Falsch** (wrong): This passage reduces the maximum points for the current stage and links back to it.
- **Weiter** (go on): This passage links to the map passage.
- **Ende** (end): This is the final passage. The total number of points is shown.

There is a debug mode that allows to enter coordinates manually. It can be turned on/off in the "Karte" passage by setting the $debug variable.
