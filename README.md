# CFB-Over-Under-Prediction-Model

**Overview**

This repository contains a predictive analytics project focused on modeling college football over/under betting outcomes. The objective is to predict whether the total points scored in a game will go over or under the closing betting line using publicly available team and game level data.

Each observation represents a single game. The response variable is binary, where a value of 1 indicates the total points exceeded the betting line (Over) and 0 indicates the total fell short (Under). Games that result in a push are excluded from the training data.

**Data Source**

All data is sourced from the cfbfastR R package, which aggregates data from the College Football Data API and ESPN play by play and game level feeds. The dataset includes team statistics, pace metrics, and betting lines that are available prior to kickoff, enabling real world predictive use.

**Features**

Input features include:
	•	Offensive and defensive team efficiency metrics
	•	Tempo and pace of play statistics
	•	Betting totals and spreads
	•	Situational variables such as home field advantage and game context

Feature engineering is designed to avoid data leakage by restricting inputs to information available before the game is played.

**Methodology**

The modeling pipeline includes:
	•	Data cleaning and preprocessing
	•	Feature engineering at the team and game level
	•	Binary classification model training
	•	Model evaluation using standard classification metrics

The emphasis of the project is on interpretability, reproducibility, and sound model design rather than pure predictive optimization.

**Files**
	•	JrichMLProject.Rmd: The full R Markdown analysis, including data processing, model construction, and evaluation.
	•	JrichMLProject.html: A rendered version of the analysis for quick review.

**Usage**

To reproduce the analysis:
	1.	JrichMLProject.Rmd.Rmd in RStudio
	2.	Install required packages listed at the top of the file
  3.  Input the 'current_week' to target which week you are trying to predict
	3.	Knit the document to HTML

Notes and Limitations
	•	Betting markets are highly efficient, and predictive performance should be interpreted cautiously.
	•	The model does not account for late breaking information such as injuries or weather changes not captured in the data.
  • The model uses a window of the past 5 weeks when determinging games. Due to this, until week 5, the model will likely underperform
