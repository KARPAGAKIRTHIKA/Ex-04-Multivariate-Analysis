# Ex-04-Multivariate-Analysis


## AIM
To perform Multivariate EDA on the given data set.

## Explanation:
Exploratory data analysis is used to understand the messages within a dataset. This technique involves many iterative processes to ensure that the cleaned data is further sorted to better understand the useful meaning.The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.

## ALGORITHM:
STEP 1
Import the built libraries required to perform EDA and outlier removal.

STEP 2
Read the given csv file

STEP 3
Convert the file into a dataframe and get information of the data.

STEP 4
Return the objects containing counts of unique values using (value_counts()).

STEP 5
Plot the counts in the form of Histogram or Bar Graph.

STEP 6
Use seaborn the bar graph comparison of data can be viewed.

STEP 7
Find the pairwise correlation of all columns in the dataframe.corr()

STEP 8
Save the final data set into the file

## PROGRAM
Name : Karpagakirthika.V

Register Number : 212221220025

import pandas as pd
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt
df=pd.read_csv("SuperStore.csv")
df
df.info()
df.describe()
df.isnull().sum()
df['Postal Code'] = df["Postal Code"].fillna(df['Postal Code'].mode()[0])
df.isnull().sum()
df.dtypes
sns.scatterplot(df['Row ID'],df['Sales'])
states=df.loc[:,["State","Sales"]]
states=states.groupby(by=["State"]).sum().sort_values(by="Sales")
plt.figure(figsize=(17,7))
sns.barplot(x=states.index,y="Sales",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("STATES")
plt.ylabel=("SALES")
plt.show()
states=df.loc[:,["State","Row ID"]]
states=states.groupby(by=["State"]).sum().sort_values(by="Row ID")
plt.figure(figsize=(17,7))
sns.barplot(x=states.index,y="Row ID",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("STATES")
plt.ylabel=("ROW ID")
plt.show()
states=df.loc[:,["Segment","Row ID"]]
states=states.groupby(by=["Segment"]).sum().sort_values(by="Row ID")
sns.barplot(x=states.index,y="Row ID",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("SEGMENT")
plt.ylabel=("ROW ID")
plt.show()
sns.barplot(df['Sales'],df['Ship Mode'],hue=df['Region'])
df.corr()
sns.heatmap(df.corr(),annot=True)

## OUTPUT

## DATA

![image](https://user-images.githubusercontent.com/103020162/230833505-85b7fdfa-d40a-49ce-892c-cd96704b86a9.png)


## Data.info

![image](https://user-images.githubusercontent.com/103020162/230833560-bf566789-bea5-46e1-8e66-fbac87e247e0.png)


## Data.describe

![image](https://user-images.githubusercontent.com/103020162/230835657-8d477ecc-72e6-40e1-9663-68ed504a7815.png)

## Checking the null values and Cleaning it

![image](https://user-images.githubusercontent.com/103020162/230834405-1da07168-6859-4560-b529-bbdaa6f7b847.png)



## DATA TYPES

![image](https://user-images.githubusercontent.com/103020162/230835437-ef3ec1a8-303a-441a-bfb8-d294ed79fccb.png)



## SCATTER PLOT

![image](https://user-images.githubusercontent.com/103020162/230835778-518d6067-cb10-471f-9e96-30c48e0a4db8.png)

## BAR PLOT

![image](https://user-images.githubusercontent.com/103020162/230835137-55cdd572-0dce-4497-85b8-1a56f42dff98.png)

![image](https://user-images.githubusercontent.com/103020162/230835161-e995dde6-7780-49b0-8a58-80465985de64.png)

![image](https://user-images.githubusercontent.com/103020162/230836682-9d4ada66-cda0-4a04-9653-82cca29118b9.png)

![image](https://user-images.githubusercontent.com/103020162/230837223-53a5f49b-dbb3-439f-a3c0-b0c5284dde56.png)




## CORRELATION COEFFICIENT INTERPRETATION

![image](https://user-images.githubusercontent.com/103020162/230837029-02f514cd-3a64-447b-bce2-fba966d6cf77.png)


## HEATMAP

![image](https://user-images.githubusercontent.com/103020162/230837067-52027eaf-a37f-4b49-946e-541e75cea65d.png)



## RESULT

Thus we have read the given data and performed the multivariate analysis with different types of plots.
