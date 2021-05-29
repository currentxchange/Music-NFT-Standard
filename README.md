# cXc Music NFT Schema Recommendation 

The cXc Music NFT Schema serves as a recommendation for any individual, collection, or application to publish a music NFT. 

The benefits of using this schema include forward compatibility (Geotags) monetizing NFT plays with traditional platform players, infinite credits and links, and more.

This Schema exists within Atomic Asset's [NFT standard](https://github.com/pinknetworkx/atomicassets-contract) on the ([atomicassets contract](https://wax.bloks.io/account/atomicassets)).

Feel free to use or modify this schema for your own purposes. 


# Summary 
This standard includes:  

Name of the NFT (Can be different than track title)

One audio file   
One video file   
Three images [Main, Back, and Promo]   

Title [If different than name]   
Album name   
Track # [If it's just one track]   

Any number of custom credits   
Any number of custom platform links   

ISO Country code  
Readable locale   
Pin as GeoJson Point   

License   
Rarity   



# Technical Summary
All media fields use IPFS.   

All other info fields are strings (except "track" is int64)  

String arrays are used to store unlimited Credits and Platform links.   
Ex.  
credits ["Band":"Boaty & The Boats","Bassist: Tim Leary", "Vocalist: Boaty McBoatface"]  
platform ["youtube.com/v/gf75ja5","soundcloud.com/my/song"] or ["Soundcloud: soundcloud.com/my/song"]



## Geo
ISO country codes [st]

Locale string intended to be used in this format "City, County, State" or corresponding values for a given locality

geotag is a GeoJson point stored as a string


License is for codes like "CC-BY", or possibly declaring some priviledge grant upon receiving NFT. 

Rarity 





| Field name | Type | Description | 
| :----:  | :----: | :----: |
| name | string | NFT name |  
| img | string | Primary image / Cover image |  
| audio | string | Audio file IPFS hash |  
| video | string | Music video file IPFS has |  
| backimg | string | Back cover of album / single |  
| promo | string | Extra image for promo poster, QR code, etc |  
| title | string | The actual title of the track |  
| album | string | Title of the album |  
| track | int64 | Number of the track on the album |  
| about | string | Description field with info about |  
| credits | string[] | Array of song credits |  
| youtube | string | Youtube URL |  
| spotify | string | Spotify URL |  
| soundcloud | string | Soundcloud URL |  
| platforms | string[] | How scarce is this NFT? |  
| nation | string | Three-letter ISO (USA, BRA, AUS, etc) |  
| locale | string | Concatanation of lower locales (State, County, City in USA) |  
| geotag | string | GeoJSON Point stored as string |  
| license | string | Declare license if needed, (CC0, etc) |  
| rarity | string | How scarce is this NFT? |  


# To use this Standard 

Paste the following array into the `idata` field using the Atomic Assets [createschema](https://wax.bloks.io/account/atomicassets?loadContract=true&tab=Actions&account=atomicassets&scope=atomicassets&limit=100&action=createschema) action to create your own schema on Atomic Assets, and then create [template](https://wax.bloks.io/account/atomicassets?loadContract=true&tab=Actions&account=atomicassets&scope=atomicassets&limit=100&action=createtemp) from the schema for each NFT you release. Because this standard uses the `string[]` (string array) type, it's currently not possible to use directly on [Atomichub](https://wax.atomichub.io/) UI, but should be in the future.

> !! Important  

Using this schema does not mean that each template must have every field filled, 
but you can only choose from fields in your future templates. You may add fields to the schema later, but not remove them. New fields will appear at the end, thus, best modify this standard to your needs before deploying.


 # cXc Music Schema 

```javascript
[
  {
    "name": "name",
    "type": "string"
  },
  {
    "name": "img",
    "type": "image"
  },
  {
    "name": "audio",
    "type": "ipfs"
  },
  {
    "name": "video",
    "type": "ipfs"
  },
  {
    "name": "backimg",
    "type": "image"
  },
  {
    "name": "promo",
    "type": "image"
  },
  {          
    "name": "title",
    "type": "string"
  },
  {
    "name": "album",
    "type": "string"
  },
  {
    "name": "track",
    "type": "int64"
  },
  {
    "name": "about",
    "type": "string"
  },
  {
    "name": "credits",
    "type": "string[]"
  },
  {
    "name": "youtube",
    "type": "string"
  },
  {
    "name": "spotify",
    "type": "string"
  },
  {
    "name": "soundcloud",
    "type": "string"
  },
  {
    "name": "platforms",
    "type": "string[]"
  },
  {
    "name": "nation",
    "type": "string"
  },
  {
    "name": "locale",
    "type": "string"
  },
  {
    "name": "geotag",
    "type": "string"
  },
  {
    "name": "license",
    "type": "string"
  },
  {
    "name": "rarity",
    "type": "string"
  }
]
```





# Modify this schema 

Change any field you wish when making your own schema 

Suggestions:

Artist - If you'd rather have your name here than in credits   
Multiple Audio fields - Duplicate the audio fields to include all songs on an album (DYOR on support)   
Metadata - Add metadata like the key, BPM, time, whatever you want   

If you'd rather include all of your links in the Platform field, you can remove the Spotify, Soundcloud, and Youtube field. Removing Youtube will also disable Youtube player from showing up on Atomichub and likely other marketplaces.


# Power of the Schema
There is no magical benefit (yet) of using this standard, just practical ones. 

In the future it's possible a mapp / dapp (like cXc) to allow users to register their own schemas that adhere to this standard, creating a Music-NFT exclusive platform that doesn't rely on accounts or collection names alone. 


# Evolution of the Schema

This schema will grow and evolve. Feel free to open issues on this repo with your suggestions.  

If you translate to another blockchain or NFT standard, please send a pull request with a file named <chain>.md in the main directory or open an issue with the code and I can update the repo if you prefer. 
