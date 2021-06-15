# Music NFT Template for Atomic Assets

Here is an example of how to format a template according to this reccommendation. You will see not every field is used, as you can use only what you need.


To do this you will have to use the [atomicassets => createtempl](https://wax.bloks.io/account/atomicassets?loadContract=true&tab=Actions&account=atomicassets&scope=atomicassets&limit=100&action=createtempl) action.

[View this template on Atomichub](https://wax.atomichub.io/explorer/template/cxcmusicnfts/166746)

    [
          {
            "key": "name",
            "value": [
              "string",
              "You are Love (Yoshi Mix) 🥇"
            ]
          },
          {
            "key": "img",
            "value": [
              "string",
              "QmfDpAGGq2UZDApqgU4m1jUxQZbJ4fLJNqzZh2SkP4dPbg"
            ]
          },
          {
            "key": "promo",
            "value": [
              "string",
              "QmYzu7Dz7LqZP3jq4zmt84rpmjWm2AfhH1SF4Et5LbxVJy"
            ]
          },
          {
            "key": "audio",
            "value": [
              "string",
              "QmcJbtB6g7Q3r4DqxqhUeDJ7wfmeBXnpJHASxjt4LM9YFV"
            ]
          },
          {
            "key": "title",
            "value": [
              "string",
              "You Are Love"
            ]
          },
          {
            "key": "about",
            "value": [
              "string",
              "A gentle reminder you are loved on a smooth Dj Quads beat, Ammon invites a grounding to Earth to hone and radiate your inner glow, and exercise your connection to All, love. We are love! Recorded on the shores of Lago Titicaca by cXc's founder, Douglas (Ammon), and mixed by Yoshi from YoshiDrops"
            ]
          },
          {
            "key": "credits",
          "value": [
            "STRING_VEC",
            ["Artist: Ammon", "Beat: Dj Quads", "Mix: Yoshi"]
          ]
        },
        {
          "key": "youtube",
          "value": [
            "string",
            "youtube.com/watch?v=45PhWLEn1m4"
          ]
        },
        {
          "key": "spotify",
          "value": [
            "string",
            "open.spotify.com/track/7qqz7yQL48CKCX6r2pvuVo?si=ff81224292ea4921"
          ]
        },
        {
          "key": "soundcloud",
          "value": [
            "string",
            "soundcloud.com/sirdouglasfresh/you-are-love"
          ]
        },
        {
          "key": "platforms",
          "value": [
            "STRING_VEC",
            ["cXc: cXc.world/?id=1048", "Apple Music: music.apple.com/us/album/you-are-love-single/1491229195", "Deezer: deezer.com/us/album/122665392"]
          ]
        },
        {
          "key": "nation",
          "value": [
            "string",
            "BOL"
          ]
        },
        {
          "key": "locale",
          "value": [
            "string",
            "Copacabana, Manco Kapac, La Paz"
          ]
        },
        {
          "key": "geotag",
          "value": [
            "string",
            "[36.060,-0.070]"
          ]
        },
        {
          "key": "license",
          "value": [
            "string",
            "CC-BY"
          ]
        },
        {
          "key": "rarity",
          "value": [
            "string",
            "Epic"
          ]
        }
      ]
