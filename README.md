# Do Looks Win Votes? Correlating Facial Features with Election Results

Final project for **COE 379L: Introduction to Machine Learning** at **The University of Texas at Austin** (December 2024).

**Team:** Diogo Costa, Inés Bafaluy, Jason Bott, Tomás Dias

📄 **[Read the report (PDF)](report.pdf)**

## Question

Research suggests that non-policy traits, such as physical appearance, may influence voters. Can a candidate's facial structure be linked to their chances of winning a U.S. presidential election?

## Method

1. **Data:** portraits of U.S. presidential candidates from 1960 (Kennedy vs. Nixon) to 2024 (Trump vs. Harris), 46 images in total, with 11 winners and 35 losers.
2. **Facial landmarks:** 68 landmarks mapped on every face with **Dlib** and **OpenCV**.
3. **Features:** the distance between every pair of landmarks (2,278 features), plus the eye ratio of each eye, for 2,280 features per face.
4. **Exploration:** Pearson correlation between each feature and electoral success, and PCA to study how linear the problem is.
5. **Models:** logistic regression, decision tree, random forest, polynomial and RBF kernel SVMs, and a multilayer perceptron, compared with 3-fold cross-validation. The **random forest** was kept because it outputs a probability of winning.

## Results

- Most of the strongest correlations involve the **eyes and eyebrows**, consistent with earlier studies.
- In the model, a smaller mouth width, higher eyebrows and smaller eyes increased the predicted probability of winning.
- The model also gave a much lower score to the two female candidates in the dataset, which reflects the **biases** of a small dataset where all past winners are men.

## Limitations

- Very small and imbalanced dataset (46 portraits)
- Lack of diversity among past candidates
- Sensitivity to head angle and facial expression in the photos
- Election outcomes depend on the opponent, not on an "ideal" face

Ideas for improvement: more candidates (Senate, Congress, other countries), MediaPipe's 468 landmarks instead of 68, and ratios instead of raw distances.

## Files

| File | Content |
|---|---|
| `report.pdf` | Final report |
| `final_project.ipynb` | Main notebook |
| `ml_model.ipynb`, `ml_model_scaled.ipynb` | Model training and comparison |
| `component_analysis.ipynb` | PCA analysis |
| `FULLDATASET.csv` | Full feature dataset |
| `landmarks_*.csv`, `normalized_landmarks_presidents.csv` | Facial landmarks |
| `pairwise_distances.csv` | Distances between landmarks |
| `correlation_results.csv` | Correlation of each feature with electoral success |
| `shape_predictor_68_face_landmarks.dat` | Dlib model used to detect the 68 landmarks |
| `OTHER/` | U.S. presidential election results, 1976–2020 |

---

Forked from [diogocravocosta/COE-379L-AI-Final-Project](https://github.com/diogocravocosta/COE-379L-AI-Final-Project).
