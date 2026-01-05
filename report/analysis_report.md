
# ChopChop User Retention Analysis

This project analyzes user behavior data from the ChopChop meal-planning web application to understand which product features most strongly influence 7-day user retention.

## Business Question

Which user behaviors and product features (e.g., ChopTrack, ChopGuide usage) are most predictive of 7-day retention?

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

## Interpretation

The results suggest that overall engagement is the strongest driver of short-term retention. Feature usage alone is not sufficient; how and when users interact with features likely matters more than binary usage indicators.

## Limitations & Next Steps

- The dataset is simulated and may not capture real-world usage patterns.
- Feature usage is treated as binary; future work could incorporate frequency and timing.
- Additional models such as tree-based methods could capture non-linear effects.
