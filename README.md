# Grammar Scoring Engine

A machine learning pipeline for automatically assessing the grammatical quality of spoken English and predicting a continuous grammar score from **0 to 5**.

The project treats grammar assessment as a speech-to-language modeling problem. Audio recordings are first processed using Automatic Speech Recognition (ASR) to obtain transcripts, which are then analyzed using linguistic features, pretrained language-model representations, and acoustic/prosodic information. These representations are combined and used to train regression models for grammar score prediction.

## Project Overview

**Input:** 45–60 second spoken English audio recordings
**Output:** Continuous grammar score between 0 and 5

The system explores the following pipeline:

```text
Audio
  ↓
Audio Preprocessing
  ↓
Automatic Speech Recognition
  ↓
Transcript
  ↓
┌────────────────────┬─────────────────────┐
│ Linguistic Features│ Language Embeddings │
└────────────────────┴─────────────────────┘
                     │
              Feature Fusion
                     │
             Regression Model
                     │
              Grammar Score
                  (0–5)
```

Model performance is evaluated using **Root Mean Squared Error (RMSE)** and **Pearson Correlation**, with cross-validation used to assess generalization.

The repository also includes exploratory analysis, preprocessing utilities, feature engineering, model benchmarking, error analysis, visualizations, and generation of the final competition submission.
