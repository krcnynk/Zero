
Status: **Editing**

Tags: [[Machine Learning]]

# Feature selection

### Filter methods
- **Correlation coefficient**: Assume Job performance= F(yoe, salary, age), we can find the correlation vector with target variable and discard/keep some subset of these features
```python
import pandas as pd 

data = { 
'Age': [25, 30, 35, 40, 45], 
'Salary': [50000, 60000, 70000, 80000, 90000], 
'Years of Experience': [2, 5, 10, 15, 20],
'Job Performance': [75, 80, 85, 90, 95] } 

df = pd.DataFrame(data) 
correlation_matrix = df.corr() 
correlation_with_target = correlation_matrix['Job Performance'] print(correlation_with_target)
```
- **Chi-square test**: Useful in categorical data
```python
import pandas as pd 
from sklearn.feature_selection import chi2 
from sklearn.preprocessing import LabelEncoder, OneHotEncoder

data = { 
'Education Level': ['Bachelor\'s', 'Master\'s', 'High School', 'PhD', 'Bachelor\'s'], 
'Gender': ['Male', 'Female', 'Male', 'Female', 'Female'], 
'Job Satisfaction': ['High', 'Medium', 'Low', 'High', 'Medium'], 
'Job Performance': ['Good', 'Average', 'Poor', 'Good', 'Average'] }

df = pd.DataFrame(data)

label_encoder = LabelEncoder()
#Assign integers to each Job Performance category
df['Job Performance'] = label_encoder.fit_transform(df['Job Performance'])

#Turns categories into one hot coded binary vectors, one vector represents all categories for one sample/individual (9 columns). drop removes rows or columns, axis=1 says columns

onehot_encoder = OneHotEncoder() 
encoded_features = onehot_encoder.fit_transform(df.drop('Job Performance', axis=1)).toarray()

chi2_stats, p_values = chi2(encoded_features, df['Job Performance']) 
feature_names = onehot_encoder.get_feature_names_out(df.columns[:-1])

chi2_results = pd.DataFrame({ 'Feature': feature_names, 'Chi2 Stat': chi2_stats, 'p-value': p_values })
```

- **ANOVA**: comparing means of different groups
	- Calculate group means
	- Calculate overall mean
	- Calculate variance between-group and within-group, divide to get F-statistics
	- Compare F-statistics to a critical value (F-distribution)
```python
import pandas as pd
from scipy import stats

# Example data
data = {
    'Diet': ['A', 'A', 'A', 'B', 'B', 'B', 'C', 'C', 'C'],
    'Weight Loss': [2.3, 2.1, 2.5, 3.1, 3.3, 3.0, 4.0, 3.8, 4.2]
}
df = pd.DataFrame(data)

# Perform One-Way ANOVA
f_statistic, p_value = stats.f_oneway(
    df[df['Diet'] == 'A']['Weight Loss'],
    df[df['Diet'] == 'B']['Weight Loss'],
    df[df['Diet'] == 'C']['Weight Loss']
)

print(f"F-Statistic: {f_statistic}")
print(f"P-Value: {p_value}")

if p_value < 0.05:
    print("Reject the null hypothesis: There is a significant difference between the group means.")
else:
    print("Fail to reject the null hypothesis: No significant difference between the group means.")

```

Two way ANOVA: has two independent variable so add "smoker"

- **Mutual Information**: Reduction in uncertainty about one variable given knowledge of other variable
```python
from sklearn.feature_selection import mutual_info_classif 
import pandas as pd 
# Example data 
data = { 'Feature1': [1, 2, 3, 4, 5],
		'Feature2': [5, 4, 3, 2, 1],
		'Target': [0, 1, 0, 1, 0] } 
		
df = pd.DataFrame(data) 
# Calculate Mutual Information 
X = df[['Feature1', 'Feature2']] 
y = df['Target'] 
mi = mutual_info_classif(X, y) 
# Display the results 
mi_series = pd.Series(mi, index=X.columns) 
print(mi_series)
```

### Wrapper methods

### Embedded methods



# References