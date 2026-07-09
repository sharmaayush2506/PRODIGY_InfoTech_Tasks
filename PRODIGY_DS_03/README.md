# Task 3 — Decision Tree Classifier for Purchase Prediction

## Objective
Build a decision tree classifier to predict whether a customer will subscribe to a term deposit based on their demographic and behavioral data, using the Bank Marketing dataset.

## Dataset
Bank Marketing Dataset (UCI Machine Learning Repository) — data from direct marketing campaigns (phone calls) of a Portuguese banking institution. 45,211 instances, 16 features after cleaning.

## Approach

### Data Cleaning
- Verified no traditional missing values (confirmed via `isnull().sum()`)
- Identified `"unknown"` as a disguised missing-value marker in categorical columns (job, education, contact, poutcome) — retained as its own category rather than dropped, since "unknown" can itself be informative
- Checked and removed exact duplicate rows
- Dropped the `duration` column intentionally to avoid data leakage, since call duration is only known after a call concludes and strongly correlates with the outcome — including it would make the model unrealistically accurate in a way that wouldn't hold in real deployment

### Preprocessing
- One-hot encoded all categorical variables (`job`, `marital`, `education`, `default`, `housing`, `loan`, `contact`, `month`, `poutcome`) using `pd.get_dummies()`, expanding the dataset to 42 columns
- Split data into features (X) and target (y), converting the target from text (yes/no) to binary (1/0)
- Performed an 80/20 train-test split using stratified sampling to preserve the class distribution across both sets, given the dataset's class imbalance

### Modeling
- Built a Decision Tree Classifier (max_depth=5 to prevent overfitting)
- Evaluated using accuracy, precision, and recall — with particular focus on the minority "Yes" class given the ~88/12 class imbalance
- Visualized the tree structure to interpret decision splits

## Tools Used
Python, Pandas, Scikit-learn, Matplotlib

## Key Findings
- The dataset is imbalanced — only ~11.7% of clients subscribed to a term deposit (5,289 out of 45,211), so accuracy alone isn't a reliable metric
- The strongest predictor was `poutcome_success` — whether the client responded positively to a *previous* marketing campaign; prior success strongly increased the likelihood of subscribing again
- Among clients without a prior successful contact, `housing_yes` (having a housing loan) was the next most influential factor — clients without a housing loan were more receptive to the offer
- Model accuracy: 89% (Precision: 0.69, Recall: 0.15 for the "Yes" class)

## Business Implication
Marketing efforts could be prioritized toward clients who responded positively in pastcampaigns,  and toward clients without existing housing loan commitments, since these were the model's strongest predictive signals for a "Yes" response.

## Files
- `task3.ipynb` — full code: cleaning, encoding, model training, evaluation
- `dataset/` — Bank Marketing dataset used