# 🎮 Mini Game System using NoSQL (MongoDB)

This project was developed as part of my 7th semester B.E. in Computer Engineering, under the subject **Big Data Analytics**. It demonstrates how to build and manage a mini game system using **MongoDB**, a NoSQL database.

---

## 📁 Database Structure

- **Database Name:** `gamesystem`
- **Collection:** `games`
- **Documents:** Each game document includes the following fields:
  - `name` (Game Name)
  - `publisher`
  - `releaseYear`
  - `genre`
  - `rating`
  - `playerScores` (Array of player objects with `playerName` and `score`)

---

## 🔧 MongoDB Operations Performed

- Inserted game data using `insertMany`
- Queried all game names
- Retrieved specific documents using `find()`
- Sorted data by `rating` (descending)
- Limited results using `limit()`
- Filtered by release year
- Updated existing documents using `updateOne`
- Added new field `achievements` in game documents

---

## 📂 Sample MongoDB Queries

```js
// 1. Show all game names
db.games.find({}, { _id: 0, name: 1 })

// 2. Find a specific game
db.games.find({ name: "pubg" })

// 3. Sort games by rating (top 3)
db.games.find().sort({ rating: -1 }).limit(3)

// 4. Filter games by release year
db.games.find({ releaseYear: 2020 }).sort({ rating: -1 })

// 5. Add achievements to a game
db.games.updateOne(
  { name: "pubg" },
  {
    $set: {
      achievements: {
        "Game Master": true,
        "Speed Demon": true
      }
    }
  }
)

🎮 Sample Games Inserted
PUBG

-GTA
-Candy Crush
-Subway Surfers
-Ludo King
-NFS Most Wanted
-Asphalt Nitro
-and others

🎯 Ratings range from 89 to 98
👥 Players: xyz, abc, def with their scores included

##🧠 Learning Outcomes
-Practical experience with NoSQL database design
-Gained understanding of embedded documents and arrays in MongoDB
-Improved query building skills with filters, sorting, and updates

##🧰 Tools Used
-MongoDB
-Mongo Shell

##📌 Project Type

-Academic Mini Project
-Subject: Big Data Analytics
-Semester: 7th
-Institute: Gujarat Technological University (GTU)
