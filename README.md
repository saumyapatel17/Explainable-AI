**Explainable AI (with a cooler name: XAI)**

Explainable AI refers to methods and techniques in the application of artificial intelligence technology such that the results of the solution can be understood by humans. In the early phases of AI adoption, it was okay to not understand what the model predicts in a certain way, as long as it gives the correct outputs. Explaining how they work was not the first priority. Now, the focus is turning to build human interpretable models.

Three important aspects of model interpretation are:
1. Transparency
2. The ability to question
3. The ease of understanding .[2]

**Model interpretability can be examined in two levels:**
1. Global Interpretation: Examines the model from a broader perspective. For example, let’s say we are working on a house price dataset and we implemented a neural network. The global interpretation might say “Your model uses # of squared feet as an important feature to derive predictions”
2. Local Interpretation: As the name suggests, this approach is focused on a certain observation/data point. Let’s continue moving forward with our example. Prediction for a really small house turned out large. Local interpretation looks at the other features and it might say “Your model predicted this way because the location of the house is very close to the city center.”

So, models take inputs and process them to get outputs. What if our data is biased? It will also make our model biased and therefore untrustworthy. It is important to understand & be able to explain to our models so that we can also trust their predictions and maybe even detect issues and fix them before presenting them to others.


**Other model interpretation techniques and libraries have been developed to overcome limitations. Some of these are :**
1. LIME ( Local Interpretable Model-Agnostic Explanations)
2. SHAP (Shapley Additive Explanations)
3. ELI5 (Explain Like I’m 5)
4. SKATER
These libraries use feature importance, partial dependence plots, individual conditional expectation plots to explain less complex models such as linear regression, logistic regression, decision trees, etc.

**LIME** (Local Interpretable Model-Agnostic Explanations): LIME is a technique used to explain the predictions of machine learning models. It works by creating simpler, interpretable models that approximate the behavior of the original complex model. LIME focuses on explaining individual predictions by highlighting the most influential features that contribute to the prediction.

**SKATER** (Model Interpretation Library): SKATER is a Python library that provides various tools for model interpretation and explanation. It offers different techniques, such as rule-based explanation, local interpretation, and global interpretation. SKATER helps understand the behavior of machine learning models and provides insights into the factors influencing their predictions.

**SHAP** (SHapley Additive exPlanations): SHAP is another model interpretation framework that aims to explain individual predictions. It assigns a value to each feature in a prediction, indicating how much each feature contributes to the prediction compared to a baseline. SHAP values provide a unified way to explain predictions across different models and enable feature importance analysis.

**ELI5** is a python package that is used to inspect ML classifiers and explain their predictions. It is popularly used to debug algorithms such as sklearn regressors and classifiers, XGBoost, CatBoost, Keras, etc. 

**Feature importance** shows how a feature is important for the model. In other words, when we delete the feature from the model, how our error changes? If the error increases a lot, this means that a feature is important for our model to predict the target variable.

**Partial dependence** plots visualize the effect of the change for a certain feature when everything else is held constant (with a cooler phrase: ceteris paribus). With the help of these, we can see a possible limit value, where this value is exceeded, it directs the model predictions the other way. When we are visualizing partial dependence plots, we are examining the model globally.

**Individual conditional expectation plots** show the effect of changes for a certain feature, just like partial dependency plots. But this time, the point of view is local. We are interested to see the effect of changes for a certain feature for all instances in our data. A partial dependence plot is the average of the lines of an ICE plot.

**When it comes to explaining more advanced models, model-agnostic (does not depend on the model) techniques are used.**
- Global surrogate models take the original inputs and your black-box machine learning predictions. When this new dataset is used to train and test the appropriate global surrogate model (more interpretable models such as linear model, decision tree, etc.), it basically tries to mimic your black-box model’s predictions. By interpreting and visualizing this “easier” model, we get a better understanding of how our actual model predicts in a certain way.