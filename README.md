# hw-05

For any exercise where you’re writing code, insert a code chunk and make
sure to label the chunk. Use a short and informative label. For any
exercise where you’re creating a plot, make sure to label all axes,
legends, etc. and give it an informative title. For any exercise where
you’re including a description and/or interpretation, use full
sentences. Make a commit at least after finishing each exercise, or
better yet, more frequently. Push your work regularly to GitHub, and make sure 
all checks pass.

For this Homework, find the types of regressions, their pros and cons, and implementation [here](https://datamineaz.org/tables/model-cheatsheet.html). 

1.  **Data selection and exploration** Here, you are tasked to select a dataset from the 2023 #tidytuesday repository that is relevant for regression analysis, including data exploration and interpretation of these results. 

    Below are the steps I recommend you follow and some guidance on what
    (not) to worry about:

    -   First, read in the data from [#tidytuesday](https://github.com/rfordatascience/tidytuesday/tree/master/data/2023), either by downloading it and placing it into a `data/` folder, or via the raw .csv link.

    -   Then, conduct exploratory data analysis: When exploring, you should:

        -   describe all columns that you will be using (data type, what the column units are, etc. Just reference the #tidytuesday README for the data)
        -   describe and interpret missing values, outliers 
        -   describe data shape and whether or not the data needs transforming
        -   correctly identify relationships that you will be examining
     
    - Finally, come up with a question to solve from the data that will be relevant for a regression


2.  **Data preprocessing**: Data preprocessing is a critical step in the pipeline of a regression analysis. It involves preparing and cleaning the data to ensure that the regression model is accurate, efficient, and relevant. Here are typical steps involved in data preprocessing for regression (but not all are necessary):

    - **Data Cleaning**:
        -   **Handling Missing Values**: Fill in missing data using techniques like mean or median imputation, or model-based methods, or drop rows/columns with missing values.
        -   **Removing Outliers**: Identify and remove anomalies that can skew the results.
    - **Data Transformation**:
        -   **Feature Scaling**: Standardize or normalize features so that they're on the same scale, which is important for methods like gradient descent to converge quickly.
        -   **Variable Transformation**: Apply transformations (e.g., log, square root, or power transformations) to deal with skewness and to satisfy model assumptions.
    - **Data Reduction**
        -   **Dimensionality Reduction**: Use techniques like Principal Component Analysis (PCA) to reduce the number of features while retaining most of the variance.
        -   **Binning/Discretization**: Convert continuous variables into categorical bins if necessary.
    - **Feature Engineering**
        -   **Creating Polynomial Features**: Add polynomial or interaction terms to model non-linear relationships.
        -   **Domain-specific Features**: Engineer new features that could have predictive power based on domain knowledge.
    - **Coding Categorical Variables**
        - Label Encoding: Transform categorical values into numerical labels (aka Dummy Variables).
    

3.  **Ordinary Least Squares (OLS) Regression** Conducting an Ordinary Least Squares (OLS) regression with resampling and evaluating the model performance involves a sequence of steps. Here's a structured approach to this exercise:

    - **Assumption Checks**:
        - Verify OLS assumptions such as linearity, independence, homoscedasticity, and normality of residuals. Its okay if your data does not meet the assumptions, but consider that you might need to transform your data first.
    - **Splitting the Dataset**:
        - Divide the dataset into training (0.8) and testing (0.2) sets to evaluate the performance of the model.
    - **Resampling**:
        -  If your data is imbalanced or if you want to improve the robustness of your model, apply resampling techniques.
        -  For cross-validation, use techniques like k-fold cross-validation.
    - **Model Building**:
        -  Using the training data, construct an OLS regression model. (Hint: see the methods in the model cheatsheet table on the course website)
    - **Model Diagnostics**:
        - Analyze the regression diagnostics from the OLS model to check for any violations of regression assumptions.
        - Examine the significance of variables using p-values.
    - **Evaluate Model Performance**:
        - Apply the model to the test set to predict the outcomes.
        - Use appropriate performance metrics (e.g., R-squared, RMSE, MAE) to evaluate the model's predictive accuracy.
    - **Interpret Results**:
        - Interpret the coefficients of the model, and assess the overall fit and predictive power.
        - Discuss the implications of your findings in the context of the problem.
    - **Review and Conclusion**:
        - Summarize the process and findings.
        - If necessary, suggest steps for further improvement, additional data collection, or alternative modeling techniques.
      
4. **Alternative Regressions**: When selecting two other regression methods beyond Ordinary Least Squares (OLS), you should consider the nature of your data and the specifics of your question. Consider the following steps when selecting your model:

   - **Feature Scaling**: Standardize or normalize features especially for methods like Ridge and Lasso which are sensitive to the scale of input variables.
   - **Hyperparameter Tuning**: Use techniques like cross-validation to find optimal parameters (e.g., Ridge regression's alpha parameter).
   - **Model Evaluation**: Evaluate the model using appropriate performance metrics and interpret the sparse coefficients.
   
   Otherwise, the steps you used for your OLS regression are also relevant here.
