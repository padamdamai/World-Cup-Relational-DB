# ⚽ World Cup Relational Database

This project is part of the **freeCodeCamp Relational Database Certification**.
It uses **PostgreSQL** and **Bash scripting** to import and analyze FIFA World Cup match data.

Repository: https://github.com/padamdamai/World-Cup-Relational-DB

---

## 📌 Project Overview

The project demonstrates how to:

* Design a **relational database**
* Import data from a **CSV file**
* Write **SQL queries** to analyze data
* Automate database operations using **Bash scripts**

The dataset contains matches from the **2014 and 2018 FIFA World Cup tournaments**.

---

## 🛠 Technologies Used

* PostgreSQL
* Bash
* SQL
* Git & GitHub

---

## 📂 Project Structure

```
World-Cup-Relational-DB
│
├── insert_data.sh      # Bash script to import CSV data into PostgreSQL
├── queries.sh          # Bash script containing SQL queries
├── games.csv           # Dataset containing World Cup match results
└── README.md           # Project documentation
```

---

## ⚙️ Database Schema

### Teams Table

| Column  | Type               |
| ------- | ------------------ |
| team_id | SERIAL PRIMARY KEY |
| name    | VARCHAR            |

### Games Table

| Column         | Type                              |
| -------------- | --------------------------------- |
| game_id        | SERIAL PRIMARY KEY                |
| year           | INT                               |
| round          | VARCHAR                           |
| winner_id      | INT (Foreign Key → teams.team_id) |
| opponent_id    | INT (Foreign Key → teams.team_id) |
| winner_goals   | INT                               |
| opponent_goals | INT                               |

---

## 📥 Importing Data

The `insert_data.sh` script reads the `games.csv` file and inserts the data into the database.

Run the script:

```
./insert_data.sh
```

This script will:

* Insert **24 unique teams**
* Insert **32 matches** into the `games` table

---

## 📊 Example Queries

The `queries.sh` script runs several SQL queries on the dataset.

Run:

```
./queries.sh
```

Example results:

### Total number of goals from winning teams

```
68
```

### Total number of goals from both teams

```
90
```

### Average goals by winning teams

```
2.13
```

### Winner of the 2018 World Cup

```
France
```

### Champions by year

```
2014 | Germany
2018 | France
```

---

## 🔎 Example SQL Query

Find the winner of the 2018 World Cup Final:

```sql
SELECT teams.name
FROM games
JOIN teams ON games.winner_id = teams.team_id
WHERE year = 2018 AND round = 'Final';
```

---

## 🚀 How to Run the Project

1. Clone the repository

```
git clone https://github.com/padamdamai/World-Cup-Relational-DB.git
```

2. Move into the project directory

```
cd World-Cup-Relational-DB
```

3. Run the data import script

```
./insert_data.sh
```

4. Run the queries

```
./queries.sh
```

---

## 📚 Learning Outcomes

Through this project I learned:

* Database normalization
* Working with PostgreSQL
* Using Bash scripts with SQL
* Importing CSV data into databases
* Writing analytical SQL queries

---

## 👨‍💻 Author

**Padam Damai**

GitHub: https://github.com/padamdamai
