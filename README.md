# Ex-04-Multivariate-Analysis
# Aim
To perform Multivariate EDA on the given data set.

# Explanation
Exploratory data analysis is used to understand the messages within a dataset. This technique involves many iterative processes to ensure that the cleaned data is further sorted to better understand the useful meaning.The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.

# Algorithm
# Step1
Import the built libraries required to perform EDA and outlier removal.

# Step2
Read the given csv file.

# Step3
Convert the file into a dataframe and get information of the data.

# Step4
Return the objects containing counts of unique values using (value_counts()).

# Step5
Plot the counts in the form of Histogram or Bar Graph.

# Step6
Use seaborn the bar graph comparison of data can be viewed.

# Step7
Find the pairwise correlation of all columns in the dataframe.corr()

# Step8
Save the final data set into the file.

# Code
```
Developed by : SAILESHKUMAR A

Registration Number : 212222230126

import pandas as pd
import numpy as py
import seaborn as sns
import matplotlib.pyplot as plt

df=pd.read_csv('SuperStore.csv')
df
df.head()
df.info()
df.describe()
df.isnull().sum()
df.dtypes

sns.scatterplot(df['Postal Code'],df['Sales'],hue=df['Row ID'])

sns.barplot(x=df['Row ID'],y=df['Sales'],data=df)

states=df.loc[:,["State","Sales"]]
states=states.groupby(by=["State"]).sum().sort_values(by="Sales")
plt.figure(figsize=(17,7))
sns.barplot(x=states.index,y="Sales",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("STATES")
plt.ylabel=("SALES")
plt.show()

sns.barplot(df['Postal Code'],df['Ship Mode'],hue=df['Region'])

df.corr()
sns.heatmap(df.corr(),annot=True)
```
# Output
# Data
![image](https://user-images.githubusercontent.com/113497410/231059203-b38b5e87-c926-4d0a-99c3-b53b08a00887.png)
# Data head
![image](https://user-images.githubusercontent.com/113497410/231059278-6002be2a-cef6-4865-879f-a78a350bdc85.png)
# Data Information
![image](https://user-images.githubusercontent.com/113497410/231059376-195cb6e6-c50f-4f24-837d-31b720979f46.png)
# Data describe
![image](https://user-images.githubusercontent.com/113497410/231059467-5fa0697f-3cd6-4fba-a3fd-8663abc8812e.png)
# Data Null Values
![image](https://user-images.githubusercontent.com/113497410/231059543-017074ce-9ae3-4fd9-9673-01f02635a45a.png)
# Data Types
![image](https://user-images.githubusercontent.com/113497410/231059646-2a0faf92-4cea-4192-8081-fe6fb7e1555a.png)
# Scatterplot
![image](https://user-images.githubusercontent.com/113497410/231059715-52482bae-9402-4fda-a0af-efc3f4d8746c.png)
# Barplot
![image](https://user-images.githubusercontent.com/113497410/231059815-90908243-e873-48d3-b5a0-eb083dfa4a63.png)

![image](https://user-images.githubusercontent.com/113497410/231059862-5b7d260e-258d-4e79-b853-9a11c835f533.png)

![image](https://user-images.githubusercontent.com/113497410/231059922-62414fef-a633-4042-bc15-c3dbfa0eb7de.png)
# Correlation and Heatmap
![image](https://user-images.githubusercontent.com/113497410/231060019-0642f42b-15bc-41e5-b13b-1db398f83823.png)

![image](https://user-images.githubusercontent.com/113497410/231060048-a88aaee5-4e72-40aa-9381-755b6631cca1.png)
# Result
Thus the program to perform EDA on the given data set is successfully executed.


