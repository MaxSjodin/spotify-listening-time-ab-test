# A/B Test: Hypothetical Product Change to Increase Listening Engagement

**Presentation:**  

[View the A/B test presentation](https://maxsjodin.github.io/spotify-listening-time-ab-test/)

This project simulates an A/B test evaluating a hypothetical product change aimed at increasing user listening time.

The goal is to assess whether the treatment leads to a meaningful improvement in listening time while ensuring no negative impact on key guardrail metrics such as churn and skip rate.

---

## Objective

Evaluate whether a product change increases user listening engagement, measured primarily through listening time, while maintaining or improving user retention and engagement quality.

---

## Dataset Overview

The dataset used in this project is sourced form Kaggle: 

- [Spotify Analysis Dataset 2025](https://www.kaggle.com/datasets/nabihazahid/spotify-dataset-for-churn-analysis?resource=download)

- User-level dataset (8000 users)
- Includes behavioral, demographic, and engagement features
- Contains treatment assignment (Control vs Treatment)
- Variables include:
  - Listening behavior (listening time, songs played, skip rate)
  - Subscription information
  - Device and demographic features
  - Retention signals (churn)

> Note: The dataset does not explicitly specify the observation window. However, the presence of weekly aggregated variables suggests a short-term behavioral snapshot.

---

## Experiment Design

- Unit of randomization: user-level
- Stratified randomization by subscription type
- 70/30 split between Control and Treatment groups
- Primary metric: Listening time
- Guardrail metrics: Churn rate, skip rate
- Statistical method: Welch’s t-test (robust to unequal variances and group sizes)

---

## Key Results

- No statistically significant effect on listening time
- Small negative average treatment effect observed
- Small differences in treatment effect across device types, with slightly negative effects for mobile and desktop and no effect for web.
- Treatment effects vary slightly across subscription types, but no clear or consistent segment-level pattern emerges.
- Slight increase in churn observed, but not statistically significant
- No meaningful change in skip rate

---

## Segment Analysis

- Only student subscriptions showed a small positive effect on listening time
- Mobile and desktop users show small negative effects
- Web users show no meaningful change

---

## Interpretation

The treatment does not demonstrate a meaningful improvement in user engagement.

Observed effects are small and inconsistent across segments, suggesting that the intervention does not meaningfully impact listening behavior.

---

## Limitations

- Moderate variability in listening behavior, reducing sensitivity to detect small effects
- Short observation window may not capture long-term behavioral changes
- Potential underpowered design for detecting small but meaningful effects
- A small increase in churn is observed in the treatment group. As a guardrail metric, it is used for directional monitoring rather than formal hypothesis testing in this analysis

---

## Next Steps

- Iterate on the treatment design to increase effect magnitude
- Consider increasing sample size or experiment duration in future tests
- Explore more targeted or personalized interventions
- Monitor churn trends in follow-up experiments
- Consider additional engagement metrics beyond listening time

---

## Tools Used

- Python (Pandas, NumPy, SciPy)
- Data visualization: Matplotlib / Seaborn
- Statistical testing: Welch’s t-test
- Jupyter Notebook / Quarto

---

## Project Structure

data/              spotify_churn_dataset.csv
notebooks/         spotify_listening_time_ab_test.ipynb
slides/            spotify_listening_time_ab_test.html
README.md