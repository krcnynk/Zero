Think of a [[Regression Model]] with independent variables. If the correlation between these independent variables is high, explaining a model will be difficult.

Increasing one variable causes other to increase linearly.

- **Structural multicollinearity**: Create new predictor using given predictors, creating x^2 using x
- **Data multicollinearity**: Poorly designed experiments, purely observational data (no restriction to the group/treatment or randomly assign)
	*An opinion survey asking questions about how people liked the most recent documentary is an example of an observational study. Here, the researchers have no control over the participants.*

**Problem**
- Correlated coefficients will jump widely if you add another independent variable
- Inflates the variance of affected variables

**Solutions** 
- Prediction only model, who cares
- Correlated variables are not a interest of study
- Correlation is not extreme
- Remove one of the correlated variable (omitted variable bias!)
- Combine correlated variables, experience + age = seniority
- partial least squares or PCA

Example: income, expenses, savings (income = expenses + savings) or dummy variable "summer"


**Detection**
Variance Inflation Factor: calculates correlation between independent variables, starts at 1 (no corr) goes up to inf.

Y = B0 + B1 X1 + B2 X2 Base regression model
X1 = B0 + B2 X2 Find regression based on others
VIF = 1/ (1-Rk^2)

[What is Multicollinearity? Extensive video + simulation!](https://www.youtube.com/watch?v=Cba9LJ9lS8s)

