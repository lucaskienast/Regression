# Regression Models
Overview of common and advanced regression techniques and libraries. Split into:

- Linear Regression
- Polynomial Regression
- Support Vector Regression
- Random Forest (Decision Tree) Regression
- Regularized/Penalized Regression

## Linear Regression
Linear regression, at it’s core, is a way of calculating the relationship between two variables. It assumes that there’s a direct correlation between the two variables, and that this relationship can be represented with a straight line. Linear regression creates a linear mathematical relationships between these two variables. It enables calculation predicting the dependent variable if the dependent variable is known.

Assumptions:

- A linear relationship is assumed between the dependent variable and the independent variables.
- Regression residuals must be normally distributed and the mean be 0.
- The residuals are homoscedastic.
- Absence of Multicollinearity is expected in the model, meaning that independent variables are not too highly correlated.
- No Autocorrelation of the residuals.

## Polynomial Regression
Polynomial Regression is a form of regression analysis in which the relationship between the independent variables and dependent variables are modeled in the nth degree polynomial. Polynomial Regression models are usually fit with the method of least squares.The least square method minimizes the variance of the coefficients,under the Gauss Markov Theorem. Polynomial Regression is a special case of Linear Regression where we fit the polynomial equation on the data with a curvilinear relationship between the dependent and independent variables.

Assumptions:

- The behavior of a dependent variable can be explained by a linear, or curvilinear, additive relationship between the dependent variable and a set of k independent variables (xi, i=1 to k).
- The relationship between the dependent variable and any independent variable is linear or curvilinear (specifically polynomial).
- The independent variables are independent of each other.
- The errors are independent, normally distributed with mean zero and a constant variance (OLS).

## Support Vector Regression
In machine learning, Support Vector Machines are supervised learning models with associated learning algorithms that analyze data used for classification and regression analysis. The objective of a support vector machine algorithm is to find a hyperplane in an n-dimensional space that distinctly classifies the data points. The data points on either side of the hyperplane that are closest to the hyperplane are called Support Vectors. These influence the position and orientation of the hyperplane and thus help build the SVM. Support Vector Regression uses the same principle as the SVMs. The basic idea behind SVR is to find the best fit line. In SVR, the best fit line is the hyperplane that has the maximum number of points. Unlike other Regression models that try to minimize the error between the real and predicted value, the SVR tries to fit the best line within a threshold value.

No model assumptions to validate for SVM.

## Decision Tree Regression
Decision Tree is one of the most commonly used, practical approaches for supervised learning. It can be used to solve both Regression and Classification tasks with the latter being put more into practical application. It is a tree-structured classifier with three types of nodes. The Root Node is the initial node which represents the entire sample and may get split further into further nodes. The Interior Nodes represent the features of a data set and the branches represent the decision rules. Finally, the Leaf Nodes represent the outcome. This algorithm is very useful for solving decision-related problems. With a particular data point, it is run completely through the entirely tree by answering True/False questions till it reaches the leaf node. The final prediction is the average of the value of the dependent variable in that particular leaf node. Through multiple iterations, the Tree is able to predict a proper value for the data point. 

Decision trees have an advantage that it is easy to understand, lesser data cleaning is required, non-linearity does not affect the model’s performance and the number of hyper-parameters to be tuned is almost null. However, it may have an over-fitting problem, which can be resolved using the Random Forest algorithm.

## Random Forest Regression
Random Forest is also a “Tree”-based algorithm that uses the qualities of multiple Decision Trees for making decisions. The term ‘Random’ is due to the fact that this algorithm is a forest of ‘Randomly created Decision Trees’. The Decision Tree algorithm has a major disadvantage in that it causes over-fitting. This problem can be limited by implementing the Random Forest Regression in place of the Decision Tree Regression. To summarize in short, The Random Forest Algorithm merges the output of multiple Decision Trees to generate the final output.

## Regularized/Penalized Regression
The standard linear model (or the ordinary least squares method) performs poorly in a situation, where you have a large multivariate data set containing a number of variables superior to the number of samples. A better alternative is the penalized regression allowing to create a linear regression model that is penalized, for having too many variables in the model, by adding a constraint in the equation. This is also known as shrinkage or regularization methods. The consequence of imposing this penalty, is to reduce (i.e. shrink) the coefficient values towards zero. This allows the less contributive variables to have a coefficient close to zero or equal zero. Note that, the shrinkage requires the selection of a tuning parameter (lambda) that determines the amount of shrinkage.

Methods:

- Ridge Regression
- LASSO Regression
- Elastic Net Regression

Generally, lasso might perform better in a situation where some of the predictors have large coefficients, and the remaining predictors have very small coefficients. Ridge regression will perform better when the outcome is a function of many predictors, all with coefficients of roughly equal size. Cross-validation methods can be used for identifying which of these two techniques is better on a particular data set.

## Ridge Regression
Ridge regression shrinks the regression coefficients, so that variables, with minor contribution to the outcome, have their coefficients close to zero. The shrinkage of the coefficients is achieved by penalizing the regression model with a penalty term called L2-norm, which is the sum of the squared coefficients. The amount of the penalty can be fine-tuned using a constant called lambda (λ). Selecting a good value for λ is critical. When λ=0, the penalty term has no effect, and ridge regression will produce the classical least square coefficients. However, as λ increases to infinite, the impact of the shrinkage penalty grows, and the ridge regression coefficients will get close zero. Note that, in contrast to the ordinary least square regression, ridge regression is highly affected by the scale of the predictors. Therefore, it is better to standardize (i.e., scale) the predictors before applying the ridge regression, so that all the predictors are on the same scale. Ridge regression shrinks the coefficients towards zero, but it will not set any of them exactly to zero. The lasso regression is an alternative that overcomes this drawback. Ridge regression will perform better when the outcome is a function of many predictors, all with coefficients of roughly equal size.

- Advantage: it still performs well, compared to the ordinary least square method, in a situation where you have a large multivariate data with the number of predictors (p) larger than the number of observations (n).
- Disadvantage: it will include all the predictors in the final model, unlike the stepwise regression methods, which will generally select models that involve a reduced set of variables.

## LASSO Regression
Lasso stands for Least Absolute Shrinkage and Selection Operator. It shrinks the regression coefficients toward zero by penalizing the regression model with a penalty term called L1-norm, which is the sum of the absolute coefficients. In the case of lasso regression, the penalty has the effect of forcing some of the coefficient estimates, with a minor contribution to the model, to be exactly equal to zero. This means that, lasso can be also seen as an alternative to the subset selection methods for performing variable selection in order to reduce the complexity of the model. As in ridge regression, selecting a good value of λ for the lasso is critical. Generally, lasso might perform better in a situation where some of the predictors have large coefficients, and the remaining predictors have very small coefficients.

- Advantage (over Ridge): it produces simpler and more interpretable models that incorporate only a reduced set of the predictors. 
- However, neither ridge regression nor the lasso will universally dominate the other.

## Elastic Net Regression
Elastic Net produces a regression model that is penalized with both the L1-norm and L2-norm. The consequence of this is to effectively shrink coefficients (like in ridge regression) and to set some coefficients to zero (as in LASSO).

## References

Abhigyan (2020) Understanding Polynomial Regression. Available at: https://medium.com/analytics-vidhya/understanding-polynomial-regression-5ac25b970e18 (Accessed: 25 August 2021)

Alam, M. (2021) A checklist for linear regression. Available at: https://towardsdatascience.com/a-checklist-for-linear-regression-bd7b3e47ea91 (Accessed: 24 August 2021)

Allison, P. (2012) When Can You Safely Ignore Multicollinearity? Available at: https://statisticalhorizons.com/multicollinearity (Accessed: 24 August 2021)

Bex, T. (2021) Intro to Regularization With Ridge And Lasso Regression with Sklearn. Available at: https://towardsdatascience.com/intro-to-regularization-with-ridge-and-lasso-regression-with-sklearn-edcf4c117b7a (Accessed: 26 August 2021)

Bhandari, A. (2020) Feature Scaling for Machine Learning: Understanding the Differnece Between Normalization vs. Standardization. Available at: https://www.analyticsvidhya.com/blog/2020/04/feature-scaling-machine-learning-normalization-standardization/ (Accessed: 24 August 2021)

Brownlee, J. (2020) How to Develop Elastic Net Regression Models in Python. Available at: https://machinelearningmastery.com/elastic-net-regression-in-python/ (Accessed: 26 August 2021)

Brownlee, J. (2021) How to Develop LASSO Regression Models in Python. Available at: https://machinelearningmastery.com/lasso-regression-with-python/ (Accessed: 26 August 2021)

Brownlee, J. (2020) How to Develop Ridge Regression Models in Python. Available at: https://machinelearningmastery.com/ridge-regression-with-python/ (Accessed: 26 August 2021)

Chatterjee, D. (2019) All the Annoying Assumptions. Available at: https://towardsdatascience.com/all-the-annoying-assumptions-31b55df246c3 (Accessed: 25 August 2025)

Godwin, J. (2021) Ridge, LASSO, and ElasticNet Regression. Available at: https://towardsdatascience.com/ridge-lasso-and-elasticnet-regression-b1f9c00ea3a3 (Accessed: 26 August 2021)

Grant, P. (2019) Understanding the Fundamentals of Linear Regression. Available at: https://towardsdatascience.com/understanding-the-fundamentals-of-linear-regression-7e64afd614e1 (Accessed: 25 August 2021)

Gurucharan, M. (2020) Machine Learning Basics: Decision Tree Regression. Available at: https://towardsdatascience.com/machine-learning-basics-decision-tree-regression-1d73ea003fda (Accessed: 25 August 2021)

Gurucharan, M. (2020) Machine Learning Basics: Multiple Linear Regression. Available at: https://towardsdatascience.com/machine-learning-basics-multiple-linear-regression-9c70f796e5e3 (Accessed: 24 August 2021)

Gurucharan, M. (2020) Machine Learning Basics: Polynomial Regression. Available at: https://towardsdatascience.com/machine-learning-basics-polynomial-regression-3f9dd30223d1 (Accessed: 25 August 2021)

Gurucharan, M. (2020) Machine Learning Basics: Random Forest Regression. Available at: https://towardsdatascience.com/machine-learning-basics-random-forest-regression-be3e1e3bb91a (Accessed: 25 August 2021)

Gurucharan, M. (2020) Machine Learning Basics: Simple Linear Regression. Available at: https://towardsdatascience.com/machine-learning-basics-simple-linear-regression-bc83c01baa07 (Accessed: 24 August 2021)

Gurucharan, M. (2020) Machine Learning Basics: Support Vector Regression. Available at: https://towardsdatascience.com/machine-learning-basics-support-vector-regression-660306ac5226 (Accessed: 26 August 2021)

Jain, A. (2016) A Complete Tutorial on Ridge and Lasso Regression in Python. Available at: https://www.analyticsvidhya.com/blog/2016/01/ridge-lasso-regression-python-complete-tutorial/ (Accessed: 25 August 2021)

Korstanje, J. (2021) Assumptions of linear regression. Available at: https://towardsdatascience.com/assumptions-of-linear-regression-fdb71ebeaa8b (Accessed: 24 August 2021)

Kumar, R. (2021) Evaluating Performance - Regression. Available at: https://medium.com/nerd-for-tech/evaluating-performance-regression-d4ef40986402 (Accessed: 26 August 2021)

Patel, D. (2021) Ridge & Lasso Regression. Available at: https://deeppatel23.medium.com/ridge-lasso-regression-4272a1990aea (Accessed: 26 August 2021)

Raj, A. (2020) Unlocking the True Power of Support Vector Regression. Available at: https://towardsdatascience.com/unlocking-the-true-power-of-support-vector-regression-847fd123a4a0 (Accessed: 25 August 2021)

Ray, S. (2015) 7 Regression Techniques you should know. Available at: https://www.analyticsvidhya.com/blog/2015/08/comprehensive-guide-regression/?utm_source=blog&utm_medium=RideandLassoRegressionarticle (Accessed: 25 August 2021)

Samaha, B. (2020) My Guide to Understanding the Assumptions of Ordinary Least Squares Regression. Available at: https://medium.com/swlh/my-guide-to-understanding-the-assumptions-of-ordinary-least-squares-regressions-b180f81801a4 (Accessed: 25 August 2021)

Sethi, A. (2020) Support Vector Regression Tutorial for Machine Learning. Available at: https://www.analyticsvidhya.com/blog/2020/03/support-vector-regression-tutorial-for-machine-learning/ (Accessed: 25 August 2021)

Sharp, T. (2020) An Introduction to Support Vector Regression. Available at: https://towardsdatascience.com/an-introduction-to-support-vector-regression-svr-a3ebc1672c2 (Accessed: 26 August 2021)

Statistics Solutions (2021) Assumptions of Linear Regression. Available at: https://www.statisticssolutions.com/free-resources/directory-of-statistical-analyses/assumptions-of-linear-regression/?__cf_chl_jschl_tk__=pmd_bNrV..YslZ4pi_s86JwRjx.e9G4YNcqvTDBQakCk8kI-1629803479-0-gqNtZGzNAjujcnBszQiR (Accessed: 24 August 2021)

STHDA (2018) Penalized Regression Essentials: Ridge, Lasso & Elastic Net. Available at: http://www.sthda.com/english/articles/37-model-selection-essentials-in-r/153-penalized-regression-essentials-ridge-lasso-elastic-net/ (Accessed: 26 August 2021)

Tan, T. (2020) Back to Basics: Assumptions of Common Machine Learning Models. Available at: https://towardsdatascience.com/back-to-basics-assumptions-of-common-machine-learning-models-e43c02325535 (Accessed: 25 August 2021)

365 Careers (2021) The Data Science Course 2021: Complete Data Science Bootcamp. Available at: https://www.udemy.com/course/the-data-science-course-complete-data-science-bootcamp/ (Accessed: 24 August 2021)
