## Search
`https://scriptblox.com/api/script/search`

### Parameters
| Parameter      | Type   | Description                                | Example Value |
|-----------------|--------|--------------------------------------------|---------------|
| `q`            | String | The search term or keyword.               | `D`           |
| `script name`  | String | Filter scripts by name or keyword.         | `5`           |
| `mode`         | String | Filter by script type (`free`, `paid`).    | `mode=free`   |

---

## What Does the API Return?
The API gives you a list of scripts based on your search. Here's how the data is organized:

### Main Data (Root)
- **`result`**: Contains all the search results.

---

### Inside `result`
| Field           | Type      | Description                       |
|------------------|-----------|-------------------------------------|
| `totalPages`    | Integer   | Total number of pages of results.   |
| `scripts`       | Array     | A list of scripts matching the search.|

---

### Each Script
Every script in the list has these details:

| Field          | Type      | Description                                                                 |
|-----------------|-----------|-------------------------------------------------------------------------------|
| `_id`          | String    | The ID for the script.                                                       |
| `title`        | String    | The name of the script.                                                      |
| `game`         | Object    | Details about the Roblox game the script is for (if it's game-specific).      |
| `script`       | String    | The script code or loadstring you can use.                                   |
| `slug`         | String    | A simplified name used in the script's link.                                 |
| `verified`     | Boolean   | Shows if the script is verified.                                             |
| `key`          | Boolean   | Shows if a key is needed to use the script.                                  |
| `keyLink`      | String    | The link to get the key (if required).                                       |
| `views`        | Integer   | How many people have viewed the script.                                      |
| `scriptType`   | String    | Tells if the script is free or paid.                                         |
| `isUniversal`  | Boolean   | Whether the script works with all Roblox games or just one.                  |
| `isPatched`    | Boolean   | Whether the script is broken or still works.                                 |
| `visibility`   | String    | Shows if the script is public or private.                                    |
| `createdAt`    | String    | When the script was first added (ISO timestamp).                             |
| `updatedAt`    | String    | When the script was last updated (ISO timestamp).                            |
| `matched`      | Array     | Highlights what parts of the script match your search.                      |

---

### Game Details (`game`)
| Field      | Type      | Description                            |
|------------|-----------|------------------------------------------|
| `gameId`   | Integer   | The ID for the game.                     |
| `name`     | String    | The name of the Roblox game.             |
| `imageUrl` | String    | A link to the game image or custom image.|

---

## Example URL

```
https://scriptblox.com/api/script/search?q=D&script name=5&mode=mode (e.g mode=free)
```

---

## Example Response
```json
{
  "result": {
    "totalPages": 840,
    "scripts": [
      {
        "_id": "673b6448ab0c0c6e307a454a",
        "title": "Nebora",
        "game": {
          "gameId": 4520749081,
          "name": "[🎃 UPD] King Legacy",
          "imageUrl": "/images/script/4520749081-1731945544740.png"
        },
        "script": "loadstring(game:HttpGet(\"https://rawscripts.net/raw/UPD-King-Legacy-Nebora-22612\"))()",
        "slug": "UPD-King-Legacy-Nebora-22612",
        "verified": true,
        "key": true,
        "keyLink": "https://discord.gg/sbUjEN6z3z",
        "views": 5747,
        "scriptType": "free",
        "isUniversal": false,
        "isPatched": false,
        "visibility": "public",
        "createdAt": "2024-11-18T15:59:04.852Z",
        "updatedAt": "2024-11-19T00:59:33.752Z",
        "matched": [
          "features",
          "game",
          "script",
          "script"
        ]
      }
    ]
  }
}
```
