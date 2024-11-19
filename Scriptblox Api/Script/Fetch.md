# Fetch
`https://scriptblox.com/api/script/fetch`

### Parameters
| Parameter | Type    | Description                                 | Example Value |
|-----------|---------|---------------------------------------------|---------------|
| `page`    | Integer | The page number to retrieve scripts from.   | `1`           |

---

## What Does the API Return?
The API returns a paginated list of scripts along with details about the Owner & Roblox games. Here's how the data is structured:

### Main Data (Root)
- **`result`**: Contains all the script data and pagination details.

---

### Inside `result`
| Field         | Type      | What It Means                                                                 |
|---------------|-----------|-------------------------------------------------------------------------------|
| `totalPages`  | Integer   | Total number of pages available.                                             |
| `nextPage`    | Integer   | The next page number, if available.                                          |
| `max`         | Integer   | Maximum number of scripts per page.                                          |
| `scripts`     | Array     | A list of scripts with detailed information.                                 |

---

### Each Script
Each script entry includes these fields:

| Field          | Type      | Description                                                                  |
|-----------------|-----------|-------------------------------------------------------------------------------|
| `_id`          | String    | The ID for the script.                                                       |
| `title`        | String    | The name of the script.                                                      |
| `game`         | Object    | Details about the Roblox game the script is associated with (if applicable). |
| `owner`        | Object    | Information about the creator of the script.                                 |
| `slug`         | String    | A simplified name used in the script link.                                   |
| `verified`     | Boolean   | Checks whether the script is verified.                                       |
| `key`          | Boolean   | Checks if a key is required to use the script.                               |
| `views`        | Integer   | The number of views the script has received.                                 |
| `scriptType`   | String    | The type of the script (`free`, `paid`).                                     |
| `isPatched`    | Boolean   | Checks whether the script is broken or still works.                          |
| `visibility`   | String    | Checks if the script is public or private.                                   |
| `createdAt`    | String    | The date and time when the script was added (ISO timestamp).                 |
| `likeCount`    | Integer   | Number of likes the script has received.                                     |
| `dislikeCount` | Integer   | Number of dislikes the script has received.                                  |

---

### Game Details (`game`)
| Field      | Type      | Description                            |
|------------|-----------|------------------------------------------|
| `gameId`   | Integer   | The ID for the game.                     |
| `name`     | String    | The name of the Roblox game.             |
| `imageUrl` | String    | A URL to the game's image.               |

---

### Owner Details (`owner`)
| Field             | Type      | Description                                                             |
|-------------------|-----------|---------------------------------------------------------------------------|
| `_id`            | String    | The ID of the script owner.                                              |
| `username`       | String    | The username of the script owner.                                        |
| `verified`       | Boolean   | Checks if the owner is verified.                                         |
| `role`           | String    | The role of the owner (e.g., `user`, `admin`).                           |
| `isBanned`       | Boolean   | Checks if the owner is banned.                                           |
| `profilePicture` | String    | URL to the profile picture of the owner.                                 |
| `createdAt`      | String    | The date when the owner account was created (ISO timestamp).             |
| `status`         | String    | The current status of the owner (e.g., `idle`, `offline`).               |

---

## Example URL
```
https://scriptblox.com/api/script/fetch?page=1
```

---

## Example Response
```json
{
  "result": {
    "totalPages": 976,
    "nextPage": 2,
    "max": 20,
    "scripts": [
      {
        "_id": "673be4fc141a4e2e19bd5143",
        "title": "Inf Exclusive Unit",
        "game": {
          "gameId": 15560168390,
          "name": "[ Trading Plaza ] Toilet Verse Tower Defense",
          "imageUrl": "https://tr.rbxcdn.com/180DAY-bcf56a15050b2bc5358e67480996ddea/500/280/Image/Jpeg/noFilter"
        },
        "owner": {
          "_id": "672bd1ddb499f2ddd69c401d",
          "username": "Hybrid",
          "verified": false,
          "role": "user",
          "isBanned": false,
          "profilePicture": "/images/photo/672bd1ddb499f2ddd69c401d-1731688776291.jpg",
          "createdAt": "2024-11-06T20:30:21.585Z",
          "status": "idle",
          "id": "672bd1ddb499f2ddd69c401d"
        },
        "slug": "Trading-Plaza-Toilet-Verse-Tower-Defense-Inf-Exclusive-Unit-22644",
        "verified": false,
        "key": true,
        "views": 168,
        "scriptType": "free",
        "isPatched": false,
        "visibility": "public",
        "createdAt": "2024-11-19T01:08:12.632Z",
        "likeCount": 0,
        "dislikeCount": 0,
        "id": "673be4fc141a4e2e19bd5143"
      }
    ]
  }
}
```
