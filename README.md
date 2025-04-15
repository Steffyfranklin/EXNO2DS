# EXNO2DS
# AIM:
      To perform Exploratory Data Analysis on the given data set.
      
# EXPLANATION:
  The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.
  
# ALGORITHM:
STEP 1: Import the required packages to perform Data Cleansing,Removing Outliers and Exploratory Data Analysis.

STEP 2: Replace the null value using any one of the method from mode,median and mean based on the dataset available.

STEP 3: Use boxplot method to analyze the outliers of the given dataset.

STEP 4: Remove the outliers using Inter Quantile Range method.

STEP 5: Use Countplot method to analyze in a graphical method for categorical data.

STEP 6: Use displot method to represent the univariate distribution of data.

STEP 7: Use cross tabulation method to quantitatively analyze the relationship between multiple variables.

STEP 8: Use heatmap method of representation to show relationships between two variables, one plotted on each axis.

## CODING AND OUTPUT
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns

dt=pd.read_csv("/content/titanic_dataset (2).csv")

dt
```
![image](https://github.com/user-attachments/assets/30293503-4335-4480-b434-32e0aa07ded4)
```
dt.info()
```
![image](https://github.com/user-attachments/assets/0c2c4230-cb03-44df-8695-920e670df545)
```
dt.shape
```
![image](https://github.com/user-attachments/assets/ca68a310-a1ce-40d9-a121-7303ef1f64f8)
```
dt.set_index("PassengerId",inplace=True)

dt.describe()
```
![image](https://github.com/user-attachments/assets/e709e0f9-461e-4bb0-b5ad-dacbf4603010)
```
dt.nunique()
```
![image](https://github.com/user-attachments/assets/4bc74690-4280-45ee-9e21-47749bc4cd81)
```
dt["Survived"].value_counts()
```
![image](https://github.com/user-attachments/assets/41a9da15-5a88-4e17-ab0c-b714109e9d2e)
```
per=(dt["Survived"].value_counts()/dt.shape[0]*100).round(2)
per
```
![image](https://github.com/user-attachments/assets/0edabae9-a633-438f-a348-0782d6045141)
```
sns.countplot(data=dt,x="Survived")
```
![image](https://github.com/user-attachments/assets/6507a871-2d8a-4bcf-8bd5-bc873769bba4)
```
dt
```
![image](https://github.com/user-attachments/assets/bbcd0733-00c3-464d-941b-60a975e42a3f)
```
dt.Pclass.unique()
```
![image](https://github.com/user-attachments/assets/2c1b6dbc-0ec8-4c60-aeda-a496d43bbf97)
```
dt.rename(columns={'Sex':'Gender'},inplace=True)
dt
```
![image](https://github.com/user-attachments/assets/62846b2f-796b-4e12-900a-d93f9fbd7f79)
```
sns.catplot(x="Gender",col="Survived",kind="count",data=dt,height=5,aspect=.7)
```
![image](https://github.com/user-attachments/assets/54d7e38d-3148-45bb-b493-e5aecc5767fd)
```
sns.catplot(x='Survived',hue="Gender",data=dt,kind="count")
```
![image](https://github.com/user-attachments/assets/23e55933-3a0b-4ff3-9989-6aaee9673fc9)
```
dt.boxplot(column="Age",by="Survived")
```
![image](https://github.com/user-attachments/assets/e03c25b4-9e9f-4826-a3df-718beda85942)
```
sns.scatterplot(x=dt["Age"],y=dt["Fare"])
```
![image](https://github.com/user-attachments/assets/417cdeb9-4c4f-4161-8811-65f17ddc0537)
```
fig,ax1=plt.subplots(figsize=(8,5))
pt=sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=dt)
```
![image](https://github.com/user-attachments/assets/c7d1d102-c9c6-4486-b631-40adc2ebf958)
```
sns.catplot(data=dt,col="Survived",x="Gender",hue="Pclass",kind="count")
```
![image](https://github.com/user-attachments/assets/b713817c-8983-4a28-b108-6f0cb0d5649d)
```
numeric_dt=dt.select_dtypes(include=['int64','float64'])
corr=numeric_dt.corr()
sns.heatmap(corr,annot=True)
```
![image](https://github.com/user-attachments/assets/0ba550fd-20fd-40a7-8b81-a78c30168e5a)
```
sns.pairplot(dt)
```
![image](https://github.com/user-attachments/assets/085bd542-21d9-4c46-84a4-75c4df16537c)

# RESULT
        Successfully perform Exploratory Data Analysis on the given data set.
