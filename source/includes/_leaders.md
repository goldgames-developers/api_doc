# Leaderboards

## Leader Object

```json
  {
    "id": 248941,
    "score": 19200,
    "rank": 1,
    "screen_name": "Joe S.",
    "board": "daily",
    "image_url": "https://avatars.derbycdn.net/15/121b70929811e491181d7fc65910e6.jpg",
    "winning_wager_count": 25
  }
```

Field | Description
--------- | -----------
id |
score | integer score, higher the better
rank | position in this board
screen_name | user chosen name
board | daily, weekly, or all_time
image_url | avatar of the user
user_id | only present in streak leaders
winning_wager_count | the total number of winning wagers a user has made (a.k.a. trophies)

## Get Leaders

`GET /leaders`

Parameter | Required? | Description
--------- | --------- | -----------
show | no | number of leaders to show (default: all)
type | no | "winnings", "streaks", "wagers" (default: winnings)
race_group_id | no | the id of a race group a leaderboard belongs to (defaults to none, giving you the global leaderboard)

<aside class="notice">
  the "wagers" type leaderboard is what is used for trophies on the front end
</aside>

### Returns

An array of `Leader` objects.

## Leaders near the current user

`GET /leaders/around_me`

### Returns

An array of `Leader` objects.

# Winners

## Winner Object

```json
 {
  "id": 1,
  "position": 1,
  "score": 10000.0,
  "date": "2018-06-20",
  "user":
    {
      "id": 2,
      "screen_name": "Jimbo",
      "image_url": "https://example.com/giphy.gif",
      "winning_wager_count": 10,
      "board": "daily"
    }
  }
```

## Get Winners

`GET /leaders/winners`

## Returns

The winners of the last 7 daily leaderboards, most recent first, in descending order of rank

