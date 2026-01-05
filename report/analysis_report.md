
# ChopChop User Retention Analysis

This project analyzes user behavior data from the ChopChop meal-planning web application to understand which product features most strongly influence 7-day user retention.

## Executive Summary

This analysis examines which product features drive 7-day user retention in the ChopChop web application. 
Using simulated event-level data, I found that overall engagement is the strongest predictor of retention. 
ChopTrack usage shows a positive association with retention, while ChopGuide usage appears more frequently among users at risk of churn.
These findings suggest that feature usage should be interpreted as behavioral signals rather than isolated metrics.

## Business Question

Which user behaviors and product features (ChopTrack, ChopGuide usage) are most predictive of 7-day retention?

## Assumptions

- User behavior patterns in the simulated data approximate realistic early-stage product usage.
- Feature usage is represented as a binary indicator rather than frequency or duration.
- 7-day retention is treated as a meaningful short-term success metric.

## Data Description

The dataset consists of simulated event-level user interaction logs, where each row represents a user action.

Key variables include:
- `event_type`: Type of user action (e.g., view_recipe, use_choptrack)
- `used_choptrack`: Whether the user used ChopTrack
- `used_chopguide`: Whether the user used ChopGuide
- `total_events`: Total number of events per user
- `retained_7d`: Whether the user returned within 7 days

## Key Findings

- Users with higher overall engagement (`total_events`) were more likely to be retained after 7 days.
- ChopTrack usage showed a small positive association with retention.
- ChopGuide usage showed a negative coefficient in the logistic regression model, suggesting that usage alone does not guarantee retention.

## Modeling Approach

A logistic regression model was used to predict 7-day retention.

Features:
- total_events
- used_choptrack
- used_chopguide

The model was chosen for its interpretability and ability to explain feature-level impact on retention.

## Model Evaluation

Model performance was evaluated using ROC AUC in addition to accuracy, as the retention outcome is moderately imbalanced.
ROC AUC provides a more robust measure of ranking performance across thresholds.


## Interpretation

The results suggest that overall engagement is the strongest driver of short-term retention. Feature usage alone is not sufficient; how and when users interact with features likely matters more than binary usage indicators.

## Limitations & Next Steps

- The dataset is simulated and may not capture real-world usage patterns.
- Feature usage is treated as binary; future work could incorporate frequency and timing.
- Additional models such as tree-based methods could capture non-linear effects.

## What I Would Do With Real Production Data

- Analyze feature usage sequences and timing effects.
- Segment users by onboarding cohort.
- Incorporate session-level metrics and dwell time.
- Test causal impact using controlled experiments or A/B testing.
