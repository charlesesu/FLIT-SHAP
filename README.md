# FLIT-SHAP
This function takes in SHAP values and the global intercept then generates the FLIT-SHAP values.

Originally, SHAP values for all features +  the global intercept = prediction for that sample/ case.
This makes it difficult to obtain the direct contribution of each feature such that their summation = the prediction.
FLIT-SHAP attempts to solve this by localizing the global intercept, such that we have local intercepts for each feature.

The simplified procedures are shown below and the function is provided in the code section.

Step 1. Generate SHAP values for your dataset, calculating the impact of each feature (X) on the model's output.

Step 2. Calculate the average absolute SHAP value for each feature across all data points.

Step 3. Sum the averages obtained in step 2 for all features to determine the fractional contribution of each X to the total.

Step 4. Calculate the global intercept (average of the predicted outputs).

Step 5. Distribute the global intercept to each feature based on its fractional contribution calculated in step 3, obtaining a localized intercept for each feature.

Step 6. Add each feature's SHAP value to its corresponding localized intercept to obtain the FLIT-SHAP values, representing the feature's contribution to the model prediction.
