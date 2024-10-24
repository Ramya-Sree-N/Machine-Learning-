### Types of data

#### 1. Numerical:

 **Represents some sort of quantitative measurement** : Heights of people, page load times, stock prices, etc.

**Discrete Data:** Integer based; often counts of some event. How many times did a customer visited HEB in a year?

**Continuous Data**
Has an infinite number of possible values. How much time did it take for a user to check out?


#### 2. Categorical:

Qualitative data that has no inherent mathematical meaning. i.e
Gender, Yes/no (binary data), Race, Country of Birth, etc.

#### 3. Ordinal:

A mixture of numerical and categorical.. i.e : movie ratings, star ratings


### Mean, Median, Mode

#### Mean: 
Also known as Average
```
Sum/(Total number of samples)
```
#### Median:
 sort the values in ascending order and take the value at the midpoint.
 if we have a even number of samples, take the average of the two values.

 #### Mode

 the most common value in the data set.


### Variance and Standard Deviation

![image](https://github.com/user-attachments/assets/4066cd95-0f7c-46ce-9f75-941ac3e10e36)

 

#### Percentile and Moments
**Percentiles:** Describe how a dataset’s values are distributed in terms of relative ranking (useful in feature scaling, ranking problems, and performance evaluation).

**Moments:** Describe the shape of the data's distribution, including its central tendency (mean), variability (variance), skewness (asymmetry), and kurtosis (tailedness), which are critical for exploratory data analysis, feature transformation, and ensuring model assumptions are met.
```
import numpy as np
import pandas as pd
import scipy.stats as stats
import matplotlib.pyplot as plt

# Create a synthetic dataset of student scores

np.random.seed(42)  # For reproducibility
scores = np.random.normal(loc=75, scale=15, size=1000)  # Normally distributed scores

# Convert to a DataFrame for better visualization

df = pd.DataFrame(scores, columns=["Scores"])

# 1. Calculate Percentiles

percentiles = [25, 50, 75]
percentile_values = np.percentile(scores, percentiles)

# Display the percentiles

for p, value in zip(percentiles, percentile_values):
    print(f"{p}th Percentile: {value:.2f}")

# 2. Calculate Moments

mean = np.mean(scores)
variance = np.var(scores)
skewness = stats.skew(scores)
kurtosis = stats.kurtosis(scores)

# Display the moments

print(f"\nMean: {mean:.2f}")
print(f"Variance: {variance:.2f}")
print(f"Skewness: {skewness:.2f}")
print(f"Kurtosis: {kurtosis:.2f}")

# Visualize the data distribution and percentiles

plt.figure(figsize=(8, 6))
plt.hist(scores, bins=30, color='skyblue', edgecolor='black', alpha=0.7)
for p, value in zip(percentiles, percentile_values):
    plt.axvline(value, color='red', linestyle='--', label=f'{p}th Percentile')

plt.title('Distribution of Student Scores with Percentiles')
plt.xlabel('Scores')
plt.ylabel('Frequency')
plt.legend()
plt.show()

```

