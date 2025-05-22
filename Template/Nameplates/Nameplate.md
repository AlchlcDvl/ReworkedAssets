# Nameplates

This folder contains the basic template for creating custom nameplates to be used for the mod. This folder has two files:
- `Template.png` - What the default nameplate looks like, if you just want to create basic nameplates, this is the file you will use.
- `Template.psd` - A photoshop variant of the template image file to allow more direct control over how the nameplate looks like.

Data is handled via the use of json files. The following will provide the template for what what data is used for the hats/visors. When copy pasting the template, make sure to delete the text that is preceded by `//`.

```json
[
    {
        // These properties are used to create a custom nameplate
        "artist": "Your Name", // Your name so that appropriate credit can be given. This is optional and if left blank or not present, it is filtered into the misc cosmetics section
        "name": "Your Cosmetic Name", // The name of the cosmetic. This is required
        "id": "fileName", // The main file id of the cosmetic. This is required
        "custom": true, // This property is used if you are replacing an existing cosmetic. This is optional and if left blank or not present, it is assumed that you are creating a new cosmetic. If set to true, it will skip the hash verification logic for the cosmetic, so that it doesn't try to update and replace your cosmetic with the existing one

        // Any other properties you see are mainly for development purposes (stream/test) or for hash verification to update assets (hash properties)
    }
]
```