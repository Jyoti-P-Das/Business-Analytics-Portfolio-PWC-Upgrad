# 🎬 RSVP Movies — SQL Database Analysis & Global Release Strategy

**Program:** Professional Certificate in Business Analytics & Consulting — upGrad × PwC Academy  
**Domain:** Entertainment Strategy · Data Engineering  
**Tools:** MySQL · SQL Workbench

---

## 🎯 Project Objective

RSVP Movies, an Indian production company, is planning a global film release in 2022. The business required a thorough data-driven analysis of three years of global film industry performance to make informed decisions on genre, director, cast, and production partnerships.

The task: design and execute 20+ SQL queries across a normalised relational database to extract insights across four analytical segments, and synthesise findings into an executive strategy document. This project demonstrates advanced SQL proficiency alongside the ability to translate database output into concrete business strategy — a core competency in data analyst and analytics engineering roles.

---

## 💼 Business Problem

RSVP's leadership needed answers to:
- Which genres perform best globally on ratings and commercial metrics — and what should the 2022 film's genre be?
- Which directors have the most consistent track record of delivering critically successful films internationally?
- Which actors and actresses should be cast for both Indian market draw and international crossover appeal?
- Which production houses are the strongest global partners based on audience reach and multilingual output?
- What is the optimal release window for a global launch?

---

## 📂 Dataset

**Source:** RSVP Movies Database — IMDb-style relational dataset (provided by upGrad as an educational SQL project; data is representative of real global film industry records)

**Database Schema — Tables Used:**

| Table | Description |
|---|---|
| `movie` | Film metadata: title, year, country, duration, worldwide gross, languages |
| `genre` | Genre per movie — many-to-many relationship with movie table |
| `ratings` | IMDb score, median rating, vote count per film |
| `director_mapping` | Maps movies to their directors |
| `role_mapping` | Maps movies to cast members with their role category |
| `names` | Person details: directors, actors, and actresses |

---

## 🔍 Analysis Performed

The analysis was structured into 4 segments, each progressively deeper in query complexity:

### Segment 1 — Movie & Genre Landscape
- Total movies released per year and per month — identified peak and off-peak windows
- Distribution of movies by genre; average genre count per film
- Average movie duration by genre
- **SQL techniques:** `GROUP BY`, `ORDER BY`, `COUNT`, `AVG`, `ROUND`

### Segment 2 — Ratings & Quality Analysis
- Films with median rating ≥ 8 shortlisted as top-tier productions
- Genre-wise average rating computed and ranked to find the most critically acclaimed categories
- Production houses with highest-rated multilingual films identified (global reach indicator)
- **SQL techniques:** `HAVING`, `WHERE` filters, multi-table `JOIN`, aggregate ranking

### Segment 3 — Talent Identification
- Directors ranked by number of hits (median rating > 8) — repeat excellence, not one-hit wonders
- Top actors filtered by average rating across Hindi-language films (Indian market priority)
- Top actress identified in Drama genre with minimum vote threshold applied (statistical reliability)
- **SQL techniques:** `RANK()`, `DENSE_RANK()`, `ROW_NUMBER()` window functions, CTEs, multiple JOINs

### Segment 4 — Global Strategy & Partner Selection
- Production houses ranked by vote count on multilingual films — audience reach proxy
- Actor-genre affinity analysis: actors with highest super-hit rates within specific genres
- Final recommendation matrix constructed: genre + director profile + cast + production partner
- **SQL techniques:** Nested subqueries, CTEs for multi-step logic, conditional aggregation

### Full SQL Technique Coverage
`INNER JOIN` · `LEFT JOIN` · Multi-table JOINs · Subqueries · `WITH` (CTEs) · `RANK()` / `DENSE_RANK()` / `ROW_NUMBER()` · `REGEXP` · `GROUP BY` / `HAVING` · `CASE WHEN` · `COUNT` / `AVG` / `SUM` / `MIN` / `MAX`

---

## 📈 Key Findings

- **Drama, Action, and Thriller** are the top 3 genres by both global volume and sustained average ratings
- Optimal release windows: **March** and **September** — historically strongest months for global openings
- A shortlist of directors with 3+ consecutive hits identified as strong international collaboration candidates
- Top multilingual production houses showed significantly higher vote counts — a reliable proxy for global audience reach
- Distinct talent pools exist for Indian domestic appeal vs international crossover — both recommended in final cast strategy

---

## 💡 Strategic Recommendations for RSVP Movies — 2022 Global Release

| Decision | Recommendation | Rationale |
|---|---|---|
| **Genre** | Drama or Thriller | Highest global ratings consistency; strong with both Indian and international audiences |
| **Director** | From top-5 hit-director shortlist | Repeat excellence > debut risk for global launch |
| **Lead Actor (India)** | Top-rated Hindi film actor (from Segment 3 shortlist) | Maximises domestic opening weekend |
| **Lead Actress (Global)** | Top Drama actress by rating + votes | Crossover appeal and award-circuit credibility |
| **Production Partner** | Top-3 multilingual house by vote count | Proven global distribution and audience reach |
| **Release Window** | March (primary) or September (secondary) | Historical data supports these windows globally |

---

## 📁 Files in This Folder

```
04-rsvp-movies-sql/
├── README.md
├── data/
│   └── IMDB_dataset.sql              ← Database schema + data (MySQL import file)
├── queries/
   └── IMDB_question.sql    ← All SQL queries — 4 segments, 20+ queries with comments
```

---

## 🎓 Skills Demonstrated

`MySQL` · `Advanced SQL` · `Complex JOINs` · `Subqueries` · `Window Functions (RANK, DENSE_RANK, ROW_NUMBER)` · `CTEs` · `Aggregate Functions` · `REGEXP` · `ERD Interpretation` · `Star Schema Understanding` · `OLAP vs OLTP Concepts` · `Analytical Thinking` · `Strategic Recommendations`

---

**Module:** Database Design and Introduction to MySQL  

