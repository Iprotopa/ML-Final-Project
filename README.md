# Machine Learning Final Project
## Neural Network vs Logistic Regression

This project compares Logistic Regression with a Neural Network using the Adult Census Income dataset.

The goal is to predict whether a person's income is above or below $50K per year and to investigate if the complexity of a neural network gives better performance than a classical machine learning model.

---

## Dataset

The Adult Census Income dataset contains numerical and categorical features such as:

- age
- education
- occupation
- hours worked per week
- sex
- race
- nationality

The target variable indicates whether a person's income is above or below $50K.

Only 23.9% of the people in the dataset belong to the higher-income class. So, both classes are not equally balanced.

---

## Preprocessing

Numerical features were processed using:

- Median imputation for missing values
- StandardScaler

Categorical features were processed using:

- Most-frequent imputation
- One-hot encoding

The dataset was divided into training and test sets.

---

## Models

Two models were compared:

### Logistic Regression

5-fold cross-validation was used to evaluate the logistic regression model.

### Neural Network

The neural network contained:

- 64-unit hidden layer with ReLU activation
- Dropout of 0.3
- 32-unit hidden layer with ReLU activation
- Sigmoid output layer

Early stopping was used during training to prevent the neural network from overfitting.

---

## Results

| Model | Accuracy | F1 Score |
|---|---:|---:|
| Logistic Regression | 0.852 | 0.656 |
| Neural Network | 0.856 | 0.661 |

The neural network achieved a slightly higher F1 score and accuracy.

The confusion matrices showed:

- Logistic Regression: 962 false negatives and 480 false positives
- Neural Network: 971 false negatives and 431 false positives

Logistic Regression recognised a few more of the higher-income cases, while the Neural Network produced fewer false positives.

---

## Comparison

The neural network achieved an F1 score of 0.661 and Logistic Regression 0.656.

Although the neural network performed a little better, the difference was small. Logistic Regression already performs well on structured tabular data and the additional complexity of the neural network is not necessary for this dataset.

Accuracy alone is not sufficient for evaluation, because the classes are not balanced. As a result, F1 score was used as the main comparison metric.

---

## Ethical Considerations

The model may reproduce existing inequalities because the dataset includes sex, race, and nationality and it may not perform equally across different groups.

False positives and false negatives can have different repercussions when the model makes decisions about benefits. If both models have similar performance, Logistic Regression may be preferable because it is simpler and easier to explain than a neural network.

---

## Reflection

The preprocessing and Logistic Regression model were straightforward to implement. The neural network was also straightforward to implement despite having more steps and parameters, as expected.

I could test different neural network architectures and investigate whether the models perform differently across demographic groups.

---

## Files

- `Final_Project_Option2.ipynb` — completed project notebook with code, results, confusion matrices, and written conclusions.
