# cXc Music NFT Standard 🎸

  Version: 0.1.4
  Total Fields: 24
  by: [cXc.world](https://cxc.world/)

# Watch the [Instructional Video](https://www.youtube.com/watch?v=GXjBQnV_Xm8) on creating your Music NFT (Works on WAX, EOS)


The cXc Music NFT Standard is a Music-Forward Atomic Assets data schema for any individual, collection, or application to make their own music NFT project. 

The benefits of using this schema include forward compatibility (Geotags) monetizing NFT plays with traditional platform players, infinite credits and links, and more.

There's no code required. You'll also see the all the code below, ready for changes if you'd rather exclude traditional players, or add extra audio fields. You can even [make a music NFT from your phone.](https://www.youtube.com/watch?v=k0vt8v5iIn4)

This Schema exists within Atomic Asset's [NFT standard](https://github.com/pinknetworkx/atomicassets-contract) on the [atomicassets contract](https://wax.bloks.io/account/atomicassets).

Feel free to use or modify this schema for any purposes in accordance with the [license]().

## Check out our NFT collection using this standard [here](https://drops.cxc.world/)


# Summary 🗞️
This standard includes:  

Name of the NFT (Can be different than track title)

One audio file   
One video file   
four images [Main, Back, Collection and Promo]   

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



# Technical Summary ⚙️
All media fields use IPFS.   

All other info fields are strings (except "track" is int64)  

String arrays are used to store unlimited Credits and Platform links.   
Ex.  
credits ["Band":"Boaty & The Boats","Bassist: Tim Leary", "Vocalist: Boaty McBoatface"]  
platform ["youtube.com/v/gf75ja5","soundcloud.com/my/song"] or ["Soundcloud: soundcloud.com/my/song"]



## Geo 🌍
ISO country codes (ISO 3166-1 alpha-3)

Locale string intended to be used in this format "City, County, State" or corresponding values for a given locality

geotag is a GeoJson point stored as a string

License is for codes like "CC-BY", or possibly declaring some priviledge grant upon receiving NFT. 

Rarity is filterable on UIs like Atomichub and wax



| Field name | Type | Description | 
| :----:  | :----: | :---- |
| name | string | NFT name |  
| img | string | Primary image / Cover image |  
| audio | string | Audio file IPFS hash |  
| video | string | Music video file IPFS hash |  
| clip | string | Additional video file IPFS hash |  
| backimg | string | Back cover of album / single |  
| promo | string | Extra image or video for promo poster, QR code, etc |  
| collectionimg | string | Extra image for Collection, optional |  
| artist | string | The artist, if you prefer a separate field to putting with other credits | 
| title | string | The actual title of the track |  
| album | string | Title of the album |  
| track | int64 | Number of the track on the album |  
| released | string | Year recorded or first released |  
| about | string | Description field with info about |  
| credits | string | Array of song credits |  
| youtube | string | Youtube URL |  
| spotify | string | Spotify URL |  
| soundcloud | string | Soundcloud URL |  
| platforms | string | A list of all platforms the music can be found, and socials if desired |  
| nation | string | Three-letter ISO (USA, BRA, AUS, etc) |  
| locale | string | Local locales (State, County, City in USA) |  
| geotag | string | GeoJSON Point stored as string |  
| license | string | Declare license if needed, (CC0, etc) |  
| rarity | string | How scarce is this NFT? Abundant Common Uncommon Rare Epic Mythic Unique |  


# To use this Standard 

Copy from this repo using the copy icon in the top-right of the code. Paste the following array into the `idata` field using the Atomic Assets [createschema](https://wax.bloks.io/account/atomicassets?loadContract=true&tab=Actions&account=atomicassets&scope=atomicassets&limit=100&action=createschema) action to create your own schema on Atomic Assets, and then create [template](https://wax.bloks.io/account/atomicassets?loadContract=true&tab=Actions&account=atomicassets&scope=atomicassets&limit=100&action=createtemp) from the schema for each NFT you release. You'll find that [here](https://github.com/currentxchange/Music-NFT-Standard/blob/main/Template%20Example.md). Because this standard uses the `string[]` (string array) type, it's currently **not possible** to use directly on [Atomichub.io](https://wax.atomichub.io/) UI, but should be in the future. For this reason, some projects (like [CAIT Drops](https://www.caittoken.io/CAIT-Drops/)) choose to implement the standard manually through the UI. *note field names must match case-sensitive to function*

> ℹ️  Important  

Using this schema does NOT mean that each template must have every field filled, 
but you can only choose from fields in your future templates. You may add fields to the schema later, but not remove them. New fields will appear at the end, thus, best to modify this standard to your needs before deploying.


# cXc Music Schema 🎸 
> Merged with Simple version (This is the Simple Version)
> Works with Atomichub UI out of the box. You can even avoid touching this code by using Create Schema on atomichub to replicate. 

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
    "name": "clip",
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
    "name": "collectionimg",
    "type": "image"
  },
  {          
    "name": "artist",
    "type": "string"
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
    "name": "year",
    "type": "string"
  },
  {
    "name": "about",
    "type": "string"
  },
  {
    "name": "credits",
    "type": "string"
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
    "type": "string"
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




# Create a Template  🛠️ 🖼️. 
Use [this example](https://github.com/currentxchange/Music-NFT-Standard/blob/main/Template%20Example.md) to create a template you can use to drop your own Music NFTs using tools like [Atomichub](https://wax.atomichub.io/) and [Neftyblocks](https://neftyblocks.com/).


# Modify this schema  🛠️

Change any field you wish when making your own schema 

Ideas:

**Artist** - If you'd rather have your name here than in credits   
**Multiple Audio fields** - Duplicate the audio fields to include all songs on an album (DYOR on marketplace support)   
**Metadata** - Add custom metadata like the key, BPM, time, whatever you want   

If you'd rather include all of your links in the Platform field, you can remove the Spotify, Soundcloud, and Youtube field. 

Removing Youtube will also disable Youtube player from showing up on Atomichub and likely other marketplaces.


# Power of the Schema ✨ 🧙‍♂️
Using this template insures maximum forward-compatibility with [music.cXc.world](https://music.cxc.world)

There is no magical benefit (yet) of using this standard, just practical ones. Youtube plays can bring extra revenue, as will the links to other players. You may credit all involved, and geographic data opens up new use cases for your NFT.  

In the future it's possible a mapp / dapp (like cXc) to allow users to register their own schemas that adhere to this standard, creating a Music-NFT exclusive platform that doesn't rely on accounts or collection names alone. 


# Evolution of the Schema 🚀 🛸

This schema will grow and evolve. Feel free to open issues on this repo with your suggestions.  

If you translate to another blockchain or NFT standard, please send a pull request adding a file named <chain>.md in the main directory containing the code needed to deploy, or open an issue with the code and I can update the repo if you prefer. 

# Mini Change Log

## 0.1.4
Changed `year` to `released`
Added Additional `clip` and img fields
Changed `promo` description to suggest video + image 
Merged Simple version, made Simple the only option. To use old version, change string to string[] ans use . This isn't recommended as there's little benefit and it's not usable through the Atomichub UI

## 0.1.3
Added `artist`, `year`, and `collectionimg`

## 0.1.2
Added `rarity` and `license`

## 0.1.1
Added `track` and `album`


 <p align="center"> ~ Created with 💜  by <a href="https://cxc.world" alt="cXc.world Music Mapp">cXc.world</a> ~ <p>
