# Ex-04-Multivariate-Analysis



AIM:

To perform Multivariate EDA on the given data set.

EXPLANATION:

Exploratory data analysis is used to understand the messages within a dataset. This technique involves many iterative processes to ensure that the cleaned data is further sorted to better understand the useful meaning.The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.

ALGORITHM:

Step1:

Import the built libraries required to perform EDA and outlier removal.

Step2:

Read the given csv file.

Step3:

Convert the file into a dataframe and get information of the data.

Step4:

Return the objects containing counts of unique values using (value_counts()).

Step5:

Plot the counts in the form of Histogram or Bar Graph.

Step6:

Use seaborn the bar graph comparison of data can be viewed.

Step7:

Find the pairwise correlation of all columns in the dataframe.corr()

Step8:

Save the final data set into the file.

PROGRAM:

Developed by :Saileshkumar A
Registration Number :212222230126

import pandas as pd

import numpy as np

import seaborn as sns

import matplotlib.pyplot as plt

df=pd.read_csv("SuperStore.csv")

df.head(6)

df.info()

df.describe()

df.isnull().sum()

df['Postal Code'] = df["Postal Code"].fillna(df['Postal Code'].mode()[0])

df.isnull().sum()

sns.scatterplot (df['Sales'])

states=df.loc[:,["State","Sales"]]

states=states.groupby(by=["State"]).sum().sort_values(by="Sales")

plt.figure(figsize=(17,7))

sbn.barplot(x=states.index,y="Sales",data=states)

plt.xticks(rotation = 90)

plt.xlabel=("STATES")

plt.ylabel=("SALES")

plt.show()

states=df.loc[:,["State","Postal Code"]]

states=states.groupby(by=["State"]).sum().sort_values(by="Postal Code")

plt.figure(figsize=(17,7))

sns.barplot(x=states.index,y="Postal Code",data=states)

plt.xticks(rotation = 90)

plt.xlabel=("STATES")

plt.ylabel=("Postal Code")

plt.show()

states=df.loc[:,["Segment","Sales"]]

states=states.groupby(by=["Segment"]).sum().sort_values(by="Sales")

#plt.figure(figsize=(10,7))

sbn.barplot(x=states.index,y="Sales",data=states)

plt.xticks(rotation = 90)

plt.xlabel=("SEGMENT")

plt.ylabel=("SALES")

plt.show()

sns.barplot(df['Postal Code'])

df.corr()

sns.heatmap(df.corr(),annot=True)



OUTPUT:

SuperStore.csv

df.head()

![image](https://user-images.githubusercontent.com/113497410/231058226-01a1c3f0-c81a-49de-9b2a-4071f06f744c.png)

df.info()

![image](https://user-images.githubusercontent.com/113497410/231058276-7d76dbfb-b7d5-414d-8779-535d9b8b0c39.png)

df.describe()

![image](https://user-images.githubusercontent.com/113497410/231058313-0b15ea04-8afd-4e1d-ba7c-9ecd2200b715.png)

describe

df.isnull().sum()

![image](https://user-images.githubusercontent.com/113497410/231058379-14188d38-dc52-442d-8914-d3e6748cb8ab.png)

AFTER CLEANING: df.isnull().sum()

![image](https://user-images.githubusercontent.com/113497410/231058409-6a796eb2-e948-482d-9d33-2b99cff42c0b.png)


after

Scatterplot

![image](https://user-images.githubusercontent.com/113497410/231058451-7cda28a4-0894-4434-bc9c-fb89f0f41e1b.png)

Barplot

![image](https://user-images.githubusercontent.com/113497410/231058505-d8b67284-d923-4131-943e-a1a29678107d.png)
![image](https://user-images.githubusercontent.com/113497410/231058527-026750b8-6cdd-46b3-9fdf-90b2018b4676.png)
![image](https://user-images.githubusercontent.com/113497410/231058557-476b0962-ea19-4be0-8619-126f58a975a7.png)

HeatMap

![image](https://user-images.githubusercontent.com/113497410/231058611-90b5c045-4fec-469e-85dc-3e19ed62d525.png)


RESULT:

Thus the program to perform EDA on the given data set is successfully executed.


