# DS_Capstone_Template
# Data Science Capstone Project 2
# NFL 4th-Down Decision Engine & Analytics Dashboard

![NFL Logo](image/NFLlogo.jpg)

## Project Overview & BLUF

### **Overview**
This project builds an end-to-end 4th-down decision engine designed to help NFL coaches make smarter, data-driven play-calling choices rather than relying purely on traditional "gut feelings." We started with deep exploratory data analysis (EDA) and a baseline Logistic Regression model, then progressed to an optimized machine learning classification pipeline (XGBoost). 

The final solution integrates a production-ready scikit-learn pipeline with an interactive, multi-view Tableau dashboard featuring a 3,619-play spatial risk map and model validation metrics.

### **Bottom Line Up Front (BLUF) Insights**
* **Clear-Cut Risk Tiers:** Our model sorts 4th downs into three actionable recommendation zones: **Green (Go)**, **Yellow (Conditional)**, and **Red (Punt/FG)**. Historical validation data proves it works—our Green go-calls achieve an actual historical success rate of **~47%**, compared to just **~4.5%** for standard Red punts/field goals.
* **Math Meets Real-World Game Pressure:** While standard baseline math discourages low-percentage long-yardage attempts, real football isn't played on a spreadsheet. Our **Yellow (Conditional)** tier highlights those tight 40–50% toss-up spots where game state pressure, score differentials, and clock urgency (like Belichick’s famous 4th-and-2 gamble or late-game playoff desperation) give coaches a clear reason to override baseline math.
* **A Ready-to-Use Coaching Tool:** By combining a serialized scikit-learn pipeline with an intuitive Tableau dashboard containing a spatial risk map and success probability metrics, we’ve bridged the gap between complex machine learning and a practical, sideline-ready tool for game day.

---

## Repository Structure

```text
├── image/                     # Project screenshots, diagrams, and logos
│   └── NFLlogo.jpg
├── models/                    # Serialized ML pipeline files (.pkl)
│   └── final_pipeline.pkl
├── data/                      # Processed datasets and play-by-play data
│   └── nfl_4th_down_cleaned.csv
├── NFL_4th_Down_Decision_Engine.ipynb   # Comprehensive project Jupyter Notebook
├── README.md                  # Project documentation & execution guide
└── .gitignore                 # Configured git ignore file







## Data Usage Guide

* **Dataset Location:** `data/nfl_4th_down_cleaned.csv`
* **Dataset Scope:** 3,619 cleaned historical 4th-down plays used for model training and Tableau visualizations.

### Key Data Columns
* `Yardline 100`: Distance in yards to the opponent's endzone (1–99).
* `Yards to Go`: Yards needed to achieve a 1st down or touchdown.
* `Score Differential`: Point difference between opponent and possessing team.
* `Decision Tier`: Model outcome classification (**Green** = Go, **Yellow** = Conditional, **Red** = Punt/FG).
* `Conversion Success`: Binary target variable (`1` = converted, `0` = failed/punted/field goal).