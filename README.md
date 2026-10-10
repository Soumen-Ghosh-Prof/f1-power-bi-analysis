# 🏎️ Formula 1 Analysis | Power BI

> Exploring the world of Formula 1 through data — from legendary drivers and championship-winning teams to race performance and reliability across different eras.

An interactive telemetry and historical analytics suite built in **Microsoft Power BI**, analyzing 70+ years of FIA Formula 1 racing data to evaluate qualifying impact, era-specific team dominance, and mechanical failure trends.

The report combines data preparation, data modelling, DAX measures, and interactive visualisations to turn raw racing data into something easier to explore and understand.

<video width="100%" controls autoplay loop muted>
<source src="media/dashboard_demo.mp4" type="video/mp4">
</video>

---

## 🎯 Key Analytical Questions

-  Which drivers and teams have won the most races?
-  How have teams and drivers performed across different F1 eras?
-  How strongly does starting position relate to winning a race?
-  How do drivers perform across their careers and individual seasons?
-  How often do drivers fail to finish, and how has reliability changed over time?

---

## 📊 Inside the Dashboard

### 🌍 1. Global Snapshot

A bird's-eye view of Formula 1 history.

![Global Snapshot Dashboard](screenshots\global_snapshot.png)

-  Total races, race entries, classified finishes, and DNFs
-  Leading team and driver statistics
-  Top 10 teams and drivers by race wins
-  Decade filters to explore different eras
-  Starting position versus win conversion rate
-  DNF breakdown by failure category

### 🏎️ 2. Team Spotlight

A closer look at a team's performance and history.

![Team Spotlight View](screenshots\team_snapshot.png)

-  Seasons contested and race entries
-  Race wins and strong finishing results
-  Points per start
-  Win rate across different decades
-  Top drivers by wins for the selected team
-  Performance breakdown
-  Team reliability and DNF breakdown

This page makes it easier to explore how a team's performance has changed over the years.

### 🧑‍✈️ 3. Driver Spotlight

A closer look at an individual driver's career.

![Driver Spotlight View](screenshots\driver_snapshot.png)

-  Seasons contested, circuits visited, race entries, wins, and pole positions
-  Average starting versus finishing position over time
-  Race wins by team
-  Race statistics, from starts to podiums and wins
-  Career reliability and DNF breakdown

Select a driver to explore their career and compare their performance across different seasons.


---

## 🔍 Interesting Findings

Here are a few patterns I noticed while exploring the data:

-  **Ferrari leads the dataset with 249 race wins.** Its wins are especially prominent in the 1950s, 1970s, and 2000s.
-  **Michael Schumacher is Ferrari's leading driver by wins** in this analysis.
- **McLaren holds the second-highest win record at 185 wins**, followed by **Mercedes** (**129**) and **Red Bull** (**122**).
-  **Lewis Hamilton leads the overall driver win count**, with **105 wins** across his time at McLaren and Mercedes, mostly with Mercedes.
-  **Max Verstappen leads the win count for the 2020s so far** in this analysis. His strongest season in the current dataset is 2023, with 19 wins.
-  **Mechanical DNFs were more common in earlier eras** and declined across later decades in the report.
-  The report shows higher win rates for drivers in the modern era than in earlier decades. Improved reliability may be one contributing factor, although the comparison alone does not establish the cause.

*These findings reflect the current report and dataset. Results may change if the data or measures are updated.*

---

## 🧩 Data Model

The project uses a relational model with dimension tables describing the main entities and fact tables recording race events and results.

![Power BI Data Model](screenshots\data_model.png)

### 📚 Dimension Tables

| Table | Purpose |
|---|---|
| `dim_drivers` | Driver information |
| `dim_teams` | team information |
| `dim_races` | Race information |
| `dim_circuits` | Circuit information |
| `dim_date` | Date-based analysis |
| `dim_status` | Race result statuses and status categories |

### 🏁 Fact Tables

| Table | Grain |
|---|---|
| `fact_results` | One row per driver in a race |
| `fact_sprint_results` | One row per driver in a sprint race |
| `fact_lap_times` | One row per driver per lap in a race |
| `fact_pit_stops` | One row per pit stop; a driver may have multiple stops in one race |

Relationships between these tables allow filters such as driver, team, circuit, date, and status to interact with the report.

Race statuses are grouped into categories to make reliability and DNF analysis easier to understand.

---

## 🛠️ Tools & Techniques

| Tool | How I used it |
|---|---|
|  **Microsoft Power BI** | Interactive reports, visualisations, and data modelling |
|  **Power Query** | Data preparation and status categorisation |
|  **DAX** | Measures and analytical calculations |
|  **Power BI Project (`.pbip`)** | Organising the report and semantic model in a project-based format |
|  **Git & GitHub** | Version control and project documentation |

---

## 🚀 Exploring the Project

1.  Open the `.pbip` project file in Power BI Desktop.
2.  Make sure the source data is available in the expected location. Raw data is not included in this repository.
3.  Refresh the model if needed.
4.  Start with **Global Snapshot**, then explore the decade filters, driver selections, and team selections.
5.  Visit **Driver Spotlight** and **Team Spotlight** to investigate individual careers and team histories.

*The exact steps needed to reconnect the source data may depend on where the files are stored on your machine.*

---

## 📚 Data Source & Attribution

- **Dataset:** Formula 1 World Championship (1950-2024) on Kaggle.
- **Original Source:** Historical data compiled from the **Ergast Motor Racing Database**.
- **Licence:** Creative Commons Attribution 4.0 International (**CC BY 4.0**).

---

## 📄 License & Disclaimer

- **Project License:** Open-source under the **MIT License**.
- **Disclaimer:** This project is an independent analytics portfolio project and is not affiliated with, endorsed by, or associated with Formula 1, the FIA, or Formula One Licensing B.V. All trademarks belong to their respective owners.

---

🏁 **Thanks for checking out the project !**
