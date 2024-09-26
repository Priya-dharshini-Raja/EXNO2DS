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
              NAME : PRIYADHARSHINI RAJA
              REG NO: 212223230160
      ``` 
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
```
```
dt=pd.read_csv("/content/titanic_dataset.csv")
dt
```
![image](https://github.com/user-attachments/assets/ce38de44-0cff-4251-92ae-66a66ecac727)
```
dt.info()
```
![image](https://github.com/user-attachments/assets/35eb69f4-01e7-4b23-9950-3cedd33a9f47)
```
dt.shape
```
![image](https://github.com/user-attachments/assets/56bfdc61-e2e9-4831-9f3c-1be5743d48c0)
```
dt.set_index("PassengerId",inplace=True)
```
```
dt.describe()
```
![image](https://github.com/user-attachments/assets/114856cf-a2ae-4b9d-a111-192e40ee4ccc)
```
dt.nunique()
```
![image](https://github.com/user-attachments/assets/4949c5e9-4f0f-420a-9827-5ad12d366c46)
```
dt["Survived"].value_counts()
```
![image](https://github.com/user-attachments/assets/9f94f6fd-2376-4c11-8a49-61b6d095e049)
```
sns.countplot(data=dt,x="Survived")
```
![image](https://github.com/user-attachments/assets/5ec4e5f3-0ce2-4d88-ba24-45e4af001a06)
```
dt
```
![image](https://github.com/user-attachments/assets/4495eafc-349d-43e5-b88e-b668bc9279ce)
```
dt.Pclass.unique()
```
![image](https://github.com/user-attachments/assets/a8f66a17-5742-4118-b44f-723715e11972)
```
dt.rename(columns={'Sex':'Gender'},inplace=True)
dt
```
![image](https://github.com/user-attachments/assets/f0219678-15e0-4a54-91ab-70099ef5f085)
```
sns.catplot(x="Gender",col="Survived",kind="count",data=dt,height=5, aspect=.7)
```
![image](https://github.com/user-attachments/assets/15fcb15f-97df-4493-9fb2-41a60ecc06f3)

```
sns.catplot(x='Survived',hue="Gender",data=dt,kind="count")
```
![image](https://github.com/user-attachments/assets/5b7ec5eb-3680-460b-88dc-9519c35f1c75)
```
dt.boxplot(column="Age",by="Survived")
```
![image](https://github.com/user-attachments/assets/5577ec42-1d45-4777-8416-163bb9c8d39b)
```
sns.scatterplot(x=dt["Age"],y=dt["Fare"])
```
![image](https://github.com/user-attachments/assets/ea26c6f1-eb2d-405a-9346-067e570cefbc)
```
sns.jointplot(x="Age",y="Fare",data=dt)
```
![image](https://github.com/user-attachments/assets/7063a8ce-b684-4814-9f91-b286c295f6be)
```
import matplotlib.pyplot as plt
fig, ax1=plt.subplots(figsize=(8,5))
pt=sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=dt)
```
![image](https://github.com/user-attachments/assets/2fd89325-c54b-47f4-9d3d-ecbd23285ce6)
```
sns.catplot(data=dt,col="Survived",x="Gender",hue="Pclass",kind="count")
```
![image](https://github.com/user-attachments/assets/aef511e3-9060-4b00-977c-f7502c01609d)
```
#co-relation
import seaborn as sns
corr=dt.corr()
sns.heatmap(corr,annot=True)
```
![image](https://github.com/user-attachments/assets/372b2e75-35b5-41b1-8cdf-84476369f4c5)
```
sns.pairplot(dt)
```
![image](https://github.com/user-attachments/assets/e2459f21-9fc1-47f3-8c5c-60a6d30a3a53)


# RESULT
       The exploratory data analysis is successfully executed using python.
