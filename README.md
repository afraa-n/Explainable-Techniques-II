# Explainable-Techniques-II: Titanic Survival Prediction

## Overview

This project explores the interpretability of a machine learning model applied to the Titanic dataset. Using explainability techniques like Partial Dependence Plots (PDP), Individual Conditional Expectation (ICE), and Accumulated Local Effects (ALE), we aim to understand how specific features—such as age, fare, and passenger class—impact the model's survival predictions.

A Random Forest Classifier is used as our model to capture complex feature interactions, and the explainability methods help us visualize the relationship between the features and the target variable.

---

## Explainability Techniques Used

- **Partial Dependence Plots (PDP):** Visualizes the average effect of a feature on the model’s predictions, giving a global view of feature influence.
  
- **Individual Conditional Expectation (ICE):** Shows individual-level feature effects across different data points, revealing variability in predictions.

- **Accumulated Local Effects (ALE):** A robust method that captures local feature effects and corrects for correlations between features, providing a more accurate interpretation than PDP.

---

## Key Objectives

1. **Feature Understanding:** Analyze how features such as age, fare, and passenger class affect the model’s predictions.
   
2. **Interpretability Comparison:** Explore the differences between PDP, ICE, and ALE to assess how each method handles feature interactions and correlations.

3. **Feature Interaction Exploration:** Use ALE to uncover and interpret feature interactions (e.g., between age and fare).

---

## Sample Results and Visualizations

#### Age and Survival Prediction (PDP)

The following PDP illustrates the general effect of **age** on survival predictions. It shows that younger passengers, particularly children, had a higher survival probability, with the likelihood decreasing as age increases.

![image](https://github.com/user-attachments/assets/b2ef7ad9-50ab-48b4-8661-e9d2d2aec291)

#### Fare and Survival Prediction (ICE)

The ICE plot reveals variability in survival probability across different fare values, highlighting how higher-paying passengers tend to have better chances of survival. The individual lines indicate different passenger profiles, showing how fare affects them differently.

![image](https://github.com/user-attachments/assets/8bd481ac-f1c3-47a8-a279-5ce21b8e000a)

#### Age and Fare Interaction (ALE - 1st Order)

Using a first-order ALE plot, we can observe the local effects of **age** and **fare** on survival. This plot provides a more accurate picture than PDP by accounting for feature correlations. The relationship between age and fare is complex, but it indicates that both features contribute to survival probability in nuanced ways.

![image](https://github.com/user-attachments/assets/0e6f8884-24d8-46e6-b1da-4ad9af4410cd)

![image](https://github.com/user-attachments/assets/362ca161-f2cd-4fee-9cba-9ce6c17bbc72)

---

## Discussion & Conclusion

#### Comparative Analysis: PDP vs ALE
- PDP tends to overestimate the effect of features, especially when there’s a correlation with other variables. This can make the effects look bigger than they really are. On the other hand, ALE gives more conservative and accurate estimates by taking into account these correlations. For example, ALE showed us that the relationship between fare and survival is more stable and consistent than PDP suggested.

- Interpretation: PDP is more intuitive and easy to understand because it gives an overall trend. However, ALE provides more accurate local effects, especially in cases with correlated features, which makes it better suited for understanding complex interactions.

#### Comparative Analysis: ICE vs Aggregated Methods
- ICE is great for seeing individual variability that’s hidden by PDP. For age, ICE showed that while the general trend was a decrease in survival probability, individual passengers could have very different outcomes based on their specific circumstances. This kind of insight is useful for understanding subgroups in the data.

- For fare, the lack of crossing lines in ICE suggests a more uniform effect, making aggregated methods like PDP and ALE more reliable for this feature.

#### Feature Impact Comparison
- Age: There’s a lot of variability in how age affects survival, with interactions playing a big role. Younger passengers clearly had an advantage, but as age increases, the situation becomes more complex, particularly when factoring in other variables like class.

- Fare: Fare is more straightforward—paying more almost always meant a higher chance of survival. The PDP, ICE, and ALE plots all tell a consistent story here, with fewer variations compared to age.

---

## Key Takeaways

1. PDP is helpful for getting an overall sense of feature importance but can overestimate effects in correlated features. ALE is more accurate and handles correlations better, making it a more reliable method in many cases.
2. ICE plots reveal individual variability, which is crucial for understanding complex features like age, where interactions with other variables significantly impact outcomes.
3. Fare is a more stable and reliable predictor of survival, while age shows more variability and depends heavily on other factors like class.
