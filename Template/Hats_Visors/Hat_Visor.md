# Hats and Visors

This folder contains the basic template for creating custom hats and visors to be used for the mod. This folder has two image files:
- `Bean.png` - The player bean sized to the correct scale. Maintain the size of the canvas and the positioning of your hat so that it matches with the bean.
- `Climb.png` - What the player looks like when they are climbing. Use this as a basis for your hat/visor that needs to be seen when going up or down ladders.

The red, green and blue areas are used to be filled in with colors relevant to the character. The red is replaced by the main color and the blue is replaced by the secondary (or shadow of the main) color. The green is replaced by the color of the visor.

Your hat/visor could implement these colors to make them adaptive to the player color (and also set by the adaptive flag in the following json).

Data is handled via the use of json files. The following will provide the template for what what data is used for the hats/visors. When copy pasting the template, make sure to delete the text that is preceded by `//`.

```jsonc
[
    {
        // These properties are shared between hats and visors.
        "artist": "Your Name", // Your name so that appropriate credit can be given. This is optional and if left blank or not present, it is filtered into the misc cosmetics section
        "name": "Your Cosmetic Name", // The name of the cosmetic. This is required
        "id": "fileName", // The main file id of the cosmetic. This is required
        "adaptive": false, // Marks the cosmetic as adaptive to the player color. This is optional and if left blank or not present, the hat/visor will not be adaptive
        "flipId": "flipName", // The flipped id of the cosmetic that appears when the is facing the other way. This is optional and if left blank or not present, the hat/visor will only be flipped normally. The flip image needs to be facing the normal direction of the cosmetic as the base game will flip it accordingly
        "climbId": "climbName", // The climbing id of the cosmetic that appears when the player is moving up or down a ladder. This is optional and if left blank or not present, the hat/visor will not appear to be on the player when when climbing
        "floorId": "floorName", // The flipped id of the cosmetic that appears when the player is being killed in some way. This is optional and if left blank or not present, the hat/visor will slide to the floor and retain its original look
        "behind": false, // Dictates whether the hat/visor will be behind the player or in front of them. This is optional and if left blank or not present, the hat/visor will be in front of the player
        "custom": true, // This property is used if you are replacing an existing cosmetic. This is optional and if left blank or not present, it is assumed that you are creating a new cosmetic. If set to true, it will skip the hash verification logic for the cosmetic, so that it doesn't try to update and replace your cosmetic with the existing one

        // This property is used to dictate the location of the preview image in the customisation tab. Normally you wouldn't need them, but some hats/visors need to be manually adjusted to allow them to exist properly in the list of cosmetics. Best to use with UnityExplorer's feature of modifying localPosition so that you don't have to restart your game often
        "chipOffset": "0,0", // "x,y"

        // The following properties are only used for hats.
        "backId": "backName", // The back id of the cosmetic that appears if the behind property is true. This is required if the behind property is true
        "backFlipId": "backFlipName", // Similar to the flipId property, but for the back id. This is optional and if left blank or not present, the back id will be flipped and shown
        "climbFlipId": "climbFlipName", // Similar to the climbId property, but for the back id. This is optional and if left blank or not present, the back id will not appear when the player is climbing
        "noBounce": true, // Dictates whether the hat will bounce on top of the player's head when they are running. This is optional and the default is true
        "blocksVisors": false, // Dictates whether the hat is mutually exclusive with visors. This is optional, the default is false

        // Any other properties you see are mainly for development purposes (stream/test) or for hash verification to update assets (hash properties), do not change them
    }
]
```

Here is the cleaned version of the json entry without the comments:

```json
[
    {
        "artist": "Your Name",
        "name": "Your Cosmetic Name",
        "id": "fileName",
        "adaptive": false,
        "flipId": "flipName",
        "climbId": "climbName",
        "floorId": "floorName",
        "behind": false,
        "custom": true,
        "chipOffset": "0,0",
        "backId": "backName",
        "backFlipId": "backFlipName",
        "climbFlipId": "climbFlipName",
        "noBounce": true
        "blocksVisors": false
    }
]
```