# Predicting-Customer-Churn-Using-Survival-Analysis-Models

Data from https://www.kaggle.com/datasets/blastchar/telco-customer-churn

Here's a detailed overview of survival analysis in English, including the background, purpose, and key concepts.

### 1. Overview
#### 1.1 Background
**What is Survival Analysis?**

Survival analysis is a statistical method for analyzing and inferring the survival time of organisms or humans based on experimental or survey data. It investigates the relationship and extent of numerous influencing factors with survival time and outcomes.

**How Does Survival Analysis Differ from Regression and Classification Models?**

Traditional classification models deal with cross-sectional data, outputting the probability of an event at a specific time snapshot. These models determine behavior (like customer churn) at the end of an observation window (e.g., a week, a month) but focus only on the outcomes, not detailing the relationship between customer churn probability and the timeline, nor predicting how changes in characteristics influence churn.

Unlike outcome-only focused models, survival analysis is concerned with both the event outcome and the timing of the event. It studies the factors affecting outcomes and the relationship between these factors and the duration until events occur, making it a crucial discipline for analyzing survival phenomena and time-to-event statistics.

**What Can Survival Analysis Be Used For?**

Survival analysis can employ methods like the Kaplan-Meier estimator to analyze survival probabilities, often used to compare survival conditions between different groups, such as analyzing retention rates among telecommunications customers with or without a streaming TV subscription. It also utilizes models like the Cox proportional hazards model to explore risk factors affecting survival, considering covariates such as customer gender, monthly fees, partnership status, and phone services.

#### 1.2 Purpose
This model uses the Python `lifelines` library to analyze features influencing telecom customer churn, predicts the probability of customer churn, and estimates customer lifetime value.

#### 1.3 Data Description
The data comes from a public dataset on Kaggle (link provided), featuring 21 variables across 7043 data points. For those unable to register and download from Kaggle, an alternative download link is available through a shared drive.

### 2. Key Concepts
#### 2.1 Events
Events in survival analysis are classified into initiation and terminal events. The initiation event marks the start of the analysis for all subjects; the terminal event is the specific outcome of interest, observed for some subjects with precise timing.

#### 2.2 Survival Time
Survival time focuses not on the absolute time of event occurrence but on the time interval from the initiation to the terminal event, such as the time taken for a patient's recovery, the duration of a first marriage, or the operational time of a system before failure.

#### 2.3 Censoring
Censoring occurs when the event timing is not observable within the study window. Right-censoring, where the start is known but the end is not, is most common. Causes include the event not occurring by the study's end, loss of contact, non-cooperation, or death from other causes.

#### 2.4 Survival Probability
Survival probability is the probability of a subject surviving from the start of the study to a specific time, denoted as S(t). It is a function of time, starting at 1 (100% survival) at time zero and decreasing over time.

#### 2.5 Median Survival Time
The median survival time, or half-life, is the time at which exactly half of the study subjects have not yet experienced the terminal event. Due to censoring, survival analysis typically uses median rather than mean survival times to describe survival.

#### 2.6 Hazard Probability
Also known as the conditional failure rate, hazard probability H(t) is the likelihood of an event occurring at time t, given survival until just before t. It is defined as h(t) = f(t)/S(t), where f(t) is the probability density function, the derivative of the cumulative distribution function F(t) = 1 - S(t).

These fundamental concepts set the stage for applying survival analysis to real-world data, providing a robust framework for understanding time-to-event data and the factors that influence such events.
