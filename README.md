# Labymod API Docs

> [!NOTE]
> This is unofficial Documentation for the LabyMod API and I am in no way associated with LabyMedia, some endpoints may be missing or incorrect.

Shouts out Neliz, LabyStudio, Northernside

## Player UUID to LabyMod User Data 
**Subdomain:** `https://dl.labymod.net/`

**Endpoint:** `GET /userdata/:dashed_uuid.json`

**Description:** This returns LabyMod user data such as cosmetics, groups, and user role.

**Request:**
```http
GET /userdata/34e57efa-5783-46c7-a9fc-890296aaba1f.json
```

**Response:**
```json
{
  "c": [ // Cosmetics
    {
      "i": 8, // Cosmetic ID
      "d": [ // Cosmetic Data
        "0a53e04c-5ed0-46e3-a522-7043aaa604a7",
        ...
      ]
    },
    ...
  ],
  "e": [ // Emote IDs
    4,
    ...
  ],
  "f": { // Flatrates
    "e": true // Emotes
  },
  "st": { // Stickers
    "p": [ // Sticker Pack IDs
      1,
      ...
    ]
  },
  "r": { // Role (Outdated use Groups instead)
    "i": 25, // Role ID
    "v": false // Visibility
  },
  "g": [ // Groups
    {
      "i": 13 // Group ID
    }
  ]
}
```

## List of LabyMod Cosmetics
**Subdomain:** `https://dl.labymod.net/`

**Endpoint:** `GET /cosmetics/index.json`

**Description:** This returns a list of every LabyMod Cosmetic.

**Request:**
```http
GET /cosmetics/index.json
```

**Response:**
```json
{
  "cosmetics": { // The Object key, Cosmetic ID and Texture Directory are the same.
    "0": {
      "id": "0",
      "type": "COSMETIC", // COSMETIC | FLYING_PET | SHOULDER_PET | WALKING_PET
      "name": "Cloak",
      "options": [
        "is_custom",
        ...
      ], // is_custom | texture | rgb | offset | side | shoulder_side | mojang_uuid
      "scale": "1",
      "attached_to": "BODY", // BODY | HEAD | LEG | ARM
      "texture_type": "USER_BOUND", // USER_BOUND | TYPE_BOUND | MOJANG_BOUND
      "hide_cape": true,
      "texture_directory": "0",
      "draft": false,
      "nametag_offset": 0,
      "default_data": [
        "1"
      ],
      "category": "CLOAK", // CLOAK | BACK | WING | FACE | HAT | BODY | HEADGEAR | SHOES | PARTNER | ARMS | PETS | AURA | LANYARD | UNDERGLOW
      "position": "BACK", // BACK | LEGS_BACK | FACE | HEAD_TOP | FEET | HIPS | ARM | CHEST | SHOULDER
      "option_list": [
        "is_custom",
        ...
      ], // is_custom | texture | rgb | offset | side | shoulder_side | mojang_uuid (OPTIONAL)
      "frame_aspect_ratio": {
        "width": 1,
        "height": 1
      }, // (OPTIONAL)
      "mirror_type": "DUPLICATE", // DUPLICATE | ROTATE (OPTIONAL)
      "mirror": true, // (OPTIONAL)
      "move_type": "BOTH", // BOTH | IDLE_ONLY | MOVE_ONLY (OPTIONAL)
      "frame_animation_delay": 500 // (OPTIONAL)
    },
    ...
  }
}
```

## Get Cosmetic Animations
**Subdomain:** `https://dl.labymod.net/`

**Endpoint:** `GET /cosmetics/:cosmetic_id/animation.json`

**Description:** This returns the animations for a cosmetic.

## Get Cosmetic Geometry
**Subdomain:** `https://dl.labymod.net/`

**Endpoint:** `GET /cosmetics/:cosmetic_id/geo.json`

**Description:** This returns the geometry for a cosmetic.

## List of LabyMod Emotes
**Subdomain:** `https://neo.labymod.net/`

**Endpoint:** `GET /cosmetics/index.json`

**Description:** This returns a list of every LabyMod Cosmetic.

**Request:**
```http
GET /cosmetics/index.json
```

**Response:**
```json
{
  "emotes": {
    "5": {
      "id": 5,
      "name": "Bow thanks",
      "attachedTo": "NONE", // NONE | ARM
      "ignoredAbortActions": [
        "MOVEMENT",
        ...
      ], // MOVEMENT | JUMPING | SPRINTING | SNEAKING | FLYING | SWIMMING | DAMAGE | ATTACKING (OPTIONAL)
      "draft": true, // Won't show up if false (OPTIONAL)
      "abortActions": [
        "MOVEMENT",
        ...
      ], // MOVEMENT | JUMPING | SPRINTING | SNEAKING | FLYING | SWIMMING | DAMAGE | ATTACKING (OPTIONAL)
      "props": true, // Won't show up if false (OPTIONAL)
      "disabledSuspensions": [
        "POSITION",
        ...
      ], // POSITION | ROTATION | SCALE (OPTIONAL)
      "textureRatio": {
        "width": 1,
        "height": 1
      }, // (OPTIONAL)
      "textureAnimationDelay": "100" // (OPTIONAL)
    },
    ...
  }
}
```

## Get Emote Animations
**Subdomain:** `https://neo.labymod.net/`

**Endpoint:** `GET /emotes/:emote_id/animation.json`

**Description:** This returns the animations for a emote.

## List of LabyMod Sticker Packs
**Subdomain:** `https://dl.labymod.net/`

**Endpoint:** `GET /stickers.json`

**Description:** This returns a list of every LabyMod Sticker pack.

**Request:**
```http
GET /stickers.json
```

**Response:**
```json
{
  "packs": [
    {
      "id": 1,
      "name": "Halloween-Pack",
      "stickers": [
        {
          "id": 1,
          "name": "Pumpkin",
          "tags": [
            "halloween",
            "kürbis",
            "pumpkin"
          ]
        },
        ...
      ]
    },
    ...
  ]
}
```

## List of LabyMod Addons & Categories
**Subdomain:** `https://dl.labymod.net/`

**Endpoint:** `GET /addons.json`

**Description:** This returns a list of every LabyMod Addon and a list of possible categories.

## Get List of LabyMod Groups
**Subdomain:** `https://dl.labymod.net/`

**Endpoint:** `GET /groups.json`

**Description:** This returns a list of every LabyMod group.

**Request:**
```http
GET /groups.json
```

**Response:**
```json
{
  "groups": [
    {
      "id": 1,
      "name": "administrator",
      "nice_name": "Administrator",
      "color_hex": "e84c3c",
      "color_minecraft": "4",
      "tag_name": "ADMIN",
      "display_type": "ABOVE_HEAD",
      "is_staff": true
    },
    ...
  ]
}
```

## Player UUID to LabyMod Cape 
**Subdomain:** `https://dl.labymod.net/`

**Endpoint:** `/capes/:dashed_uuid`

**Description:** This returns an image of a users LabyMod cape.


## Get List of LabyMod Server Groups
**Subdomain:** `https://dl.labymod.net/`

**Endpoint:** `GET /server_groups.json`

**Description:** This returns a list of every LabyMod Server group.

**Request:**
```http
GET /server_groups.json
```

**Response:**
```json
{
  "server_groups": {
    "timolia": {
      "server_name": "timolia",
      "nice_name": "Timolia",
      "direct_ip": "play.timolia.de",
      "wildcards": [
        "%.timolia.de"
      ],
      "attachments": [
        {
          "file_name": "background.png",
          "url": "https://dl.labymod.net/img/server/timolia/background.png",
          "hash": "755ee9fd241921bedc0279986f4b0c50"
        },
        {
          "file_name": "background.webp",
          "url": "https://dl.labymod.net/img/server/timolia/background.webp",
          "hash": "b677cdc0cd2d6f877a72a0a6fb6095c9"
        },
        {
          "file_name": "background@2x.png",
          "url": "https://dl.labymod.net/img/server/timolia/background@2x.png",
          "hash": "943f4516c38e4dc054db7a32126c0e36"
        },
        {
          "file_name": "background@2x.webp",
          "url": "https://dl.labymod.net/img/server/timolia/background@2x.webp",
          "hash": "10cfbd430fcb3f8c7e7391f7a8ba71d3"
        },
        {
          "file_name": "banner.png",
          "url": "https://dl.labymod.net/img/server/timolia/banner.png",
          "hash": "289b7bff8ecc8879e23f676ef2524465"
        },
        {
          "file_name": "banner.webp",
          "url": "https://dl.labymod.net/img/server/timolia/banner.webp",
          "hash": "2eb71b4f3e27f3026137a6d1faed1332"
        },
        {
          "file_name": "icon.png",
          "url": "https://dl.labymod.net/img/server/timolia/icon.png",
          "hash": "e3dcfd2748b10d124bcc7a8aeeeca07b"
        },
        {
          "file_name": "icon.webp",
          "url": "https://dl.labymod.net/img/server/timolia/icon.webp",
          "hash": "fa935d1cd9443261886a06a1a15d28c2"
        },
        {
          "file_name": "icon@2x.png",
          "url": "https://dl.labymod.net/img/server/timolia/icon@2x.png",
          "hash": "507e37715b1a823ccc4d826ff118367a"
        },
        {
          "file_name": "icon@2x.webp",
          "url": "https://dl.labymod.net/img/server/timolia/icon@2x.webp",
          "hash": "34ad6c4d676bff210794b09391ae4fe8"
        },
        {
          "file_name": "logo.png",
          "url": "https://dl.labymod.net/img/server/timolia/logo.png",
          "hash": "e3dcfd2748b10d124bcc7a8aeeeca07b"
        },
        {
          "file_name": "logo@2x.png",
          "url": "https://dl.labymod.net/img/server/timolia/logo@2x.png",
          "hash": "507e37715b1a823ccc4d826ff118367a"
        },
        {
          "file_name": "manifest.json",
          "url": "https://dl.labymod.net/img/server/timolia/manifest.json",
          "hash": "22324ed62c01642e1f59627dca634fe8"
        }
      ],
      "social": {
        "web": "https://timolia.de",
        "web_shop": "https://shop.timolia.de",
        "twitter": "TimoliaTeam",
        "discord": "https://discord.gg/Q55FujN",
        "tiktok": "timolianetwork",
        "youtube": "https://www.youtube.com/Timolia",
        "instagram": "timolianetwork"
      },
      "gamemodes": {
        "jumpworld": {
          "name": "JumpWorld",
          "command": "/quickjoin jumpworld",
          "url": "https://www.timolia.de/games#jumpworld",
          "color": "#0095B0",
          "versions": "1.20<*"
        },
        "pvp": {
          "name": "1vs1",
          "command": "/quickjoin pvp",
          "url": "https://www.timolia.de/games#pvp",
          "color": "#0095B0"
        },
        "freebuild": {
          "name": "Freebuild",
          "command": "/quickjoin freebuild",
          "url": "https://www.timolia.de/games#freebuild",
          "color": "#0095B0",
          "versions": "1.20<*"
        },
        "brainbow": {
          "name": "BrainBow",
          "command": "/quickjoin brainbow",
          "url": "https://howto.timolia.de/games/brainbow/",
          "color": "#0095B0"
        },
        "4rena": {
          "name": "4rena",
          "command": "/quickjoin 4rena",
          "url": "https://www.timolia.de/games#4rena",
          "color": "#0095B0"
        },
        "castles": {
          "name": "Castles",
          "command": "/quickjoin castles",
          "url": "https://www.timolia.de/games#castles",
          "color": "#0095B0"
        },
        "survivalquest": {
          "name": "SurvivalQuest",
          "command": "/quickjoin survivalquest",
          "url": "https://www.timolia.de/games#survivalquest",
          "color": "#0095B0",
          "versions": "1.16.5<*"
        },
        "splun": {
          "name": "Splun",
          "command": "/quickjoin splun",
          "url": "https://www.timolia.de/games#splun",
          "color": "#0095B0",
          "versions": "1.20<*"
        }
      },
      "chat": {
        "message_formats": [
          "^\u00a7[a-f0-9](?<level>\\d+)( \\||\u00a78 \\|) \u00a7[a-f0-9](?<sender>[a-zA-Z0-9_]{2,16})\u00a7r\u00a77: \u00a7f(?<message>.*)$"
        ]
      },
      "user_stats": "https://www.timolia.de/stats/{userName}"
    }
    ...
  }
}

```
