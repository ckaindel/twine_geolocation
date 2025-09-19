This sample code provides minimum functionality to use geolocation on mobile devices in Twine/Sugarcube. Just import the Twee file into Twine. Functions are defined in the Story Javascript and called in the "Karte" passage.

The stages of the scavenger hunt are stored in the $markers object, defined in the "StoryInit" passage. It holds the coordinates as an array and the target passage. $stages is set to 0 in "StoryInit" and advances with every stage completed.

The map is embedded in the "Karte" passage. It shows icons for the player and the target and is updated every 5 seconds. A popup linked to the target passage opens when the player reaches the target.

Events at the stages are handled by standard Twine code. Once a stage is finished, the player is directed back to the "Karte" passage. The map opens again and the target marker moves to the next stage. 

There is a debug mode that allows to enter coordinates manually. It can be turned on/off in the "Karte" passage by setting the $debug variable.
