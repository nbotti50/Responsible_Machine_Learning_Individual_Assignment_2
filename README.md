# Responsible_Machine_Learning_Individual_Assignment_2 - COMPAS Analysis

## The Purpose of the Analysis

The purpose of the second individual assignment involves evaluating the fairness and predictive performance of the COMPAS risk assessment. The analysis examines recidivism outcomes across demographic groups, specifically comparing African-American defendants to White defendants. Explainability tools identify why the model assigns specific scores and determine if bias exists.

This analysis used statistical tools such as logistic regression, Cox proportional hazards models, and Kaplan-Meier survival analysis to deeply investigate how well the model predicts recidivism and if those predictions are consistent across groups. Additionally, explainability tools such as DiCE, SHAP, and Lime were used to identify feature influence in the predictions the model outputs. Here is how these tools were used more specifically: 

- Logistic Regression was used to model the likelihood of a defendant receiving a high COMPAS risk score, while controlling for factors such as age, prior offenses, gender, and race. This helped identify whether certain groups were more likely to be assigned higher risk scores, holding other variables constant.

- Cox Proportional Hazards Models were used to examine the relationship between risk scores and the timing of recidivism. This allowed for an assessment of how well the COMPAS scores align with actual outcomes over time, and whether the model’s predictive performance differs across demographic groups.

- Kaplan-Meier Survival Analysis was used to estimate the probability of not recidivating over time for different risk score categories. By comparing survival curves across groups, this method provided a visual and statistical way to evaluate how well the score separates low, medium, and high-risk individuals.

- LIME (Local Interpretable Model-agnostic Explanations) was used to examine individual defendants to identify specific factors causing high risk scores.

- SHAP (Shapley Additive Explanations) was used to provide a global view of variable importance. It informs us what features globally and locally influence output predictions, if one feature were to change, how that would alter predictions and to what magnitutde.

- DiCE (Diverse Counterfactual Explanations) was used to not only see what influenced the prediction, but reveal what would have to change in order for the model to predict a different outcome, potentially revealing immutable feature changes that raise a red flag.

---

## Python Libraries Used

The following Python libraries were used in this analysis (and, the purpose and use of these tools are listed next to it:

- `pandas` – used for data cleaning, filtering, and structuring the dataset. This involved removing invalid observations, making new variables such as categorical factors for race and score levels, and preparing the data.
- `numpy` – used for numerical operations and transformations (handling arrays, converting data types) and performing calculations needed for probability and the interpretation of modeling.
- `matplotlib` – used to visualize results of the Kaplan-Meier survival curves, acting as a visual ad for identifying different recidivism patterns across different risk score groups and demographics.
- `scikit-learn` – used to implement logistic regression models that estimate the likelihood of being assigned a high COMPAS risk score. This allowed for analysis of how different variables, including race, are associated with predicted risk. 
- `lifelines` – used for survival analysis, including Cox proportional hazards models and Kaplan-Meier estimation.
- `lifelines` – Used for local interpretability to explain individual defendant risk scores.
- `shap` – Used for both local and global feature importance analysis.
- `dice-ml` - Used to generate counterfactual explanations for model predictions.
---

## Instructions for Reproducing the Results

To reproduce the results of this analysis, follow the steps below:

1. **Install required packages**  
   Run the following command in a notebook cell or terminal:

   ```python
   !pip install pandas numpy matplotlib scikit-learn lifelines lime shap dice-ml
2. **Download .ipynb file and run all cells**
3. **Review the findings in a high-level summary in the Governance Memo**
4. **Note: No manual download of files is required. URLs retrieve data in the notebook, getting CSV files from another GitHub repository: https://github.com/propublica/compas-analysis/tree/master**

A Statement on AI Usage: Google Gemini, embedded in Google Colab (the tool used to create the notebook), was used to identify a complex error message and guide thinking on how to solve it. Additionally, external internet sources, such as OpenStack, were used to identify Python packages that most closely reflect the R packages used in the notebook that needed to be translated into Python. All code was written and reviewed by me, ensuring that important statistical analyses from the R notebook were present in the Python version, and extensive conclusions and interpretations were made from the outputs given by the code. 
