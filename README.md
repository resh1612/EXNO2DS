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
 df=pd.read_csv("/content/titanic_dataset.csv")
 df
```

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/f007ea11-8cd5-4b55-92cf-8ce89ff72b42" />

```
 df.info()
```

<img width="1326" height="459" alt="image" src="https://github.com/user-attachments/assets/0e4553c3-b3ae-4dee-b668-c853600896b0" />

```
df.describe()
```

<img width="1008" height="376" alt="image" src="https://github.com/user-attachments/assets/5c5af1ea-c07e-48de-95f6-d0d38b016da1" />


```
df.dtypes
```

<img width="340" height="455" alt="image" src="https://github.com/user-attachments/assets/9576a120-73d0-4ccf-b488-9ab5ef203fa3" />

```
df.shape
```

<img width="223" height="98" alt="image" src="https://github.com/user-attachments/assets/9ca313d5-d014-4ed9-b207-84e9b709edbe" />

```
df.value_counts()
```

<img width="1296" height="486" alt="image" src="https://github.com/user-attachments/assets/82562557-f7d9-4eca-8780-1f9f239a5a93" />

```
df['Age'].value_counts()
```

<img width="347" height="468" alt="image" src="https://github.com/user-attachments/assets/24d2f94c-6432-42d7-b6f5-a6553ca0d2b8" />

```
df.set_index("PassengerId", inplace=True)
df
```

<img width="1247" height="486" alt="image" src="https://github.com/user-attachments/assets/c8cd3d95-a59e-4c8c-bf31-ddf1dcf1be56" />

```
df.nunique()
```

<img width="310" height="455" alt="image" src="https://github.com/user-attachments/assets/d532333e-a176-433e-a771-179045954e6f" />

```
sns.countplot(data=df,x='Survived')
```

<img width="755" height="478" alt="image" src="https://github.com/user-attachments/assets/ac11d7fd-bcd9-4a76-8e9d-dcff2c6ca1ce" />

```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```

<img width="1272" height="460" alt="image" src="https://github.com/user-attachments/assets/2e56af49-7676-4067-9535-63d953e3c723" />

```
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect= 0,5)
```

<img width="724" height="459" alt="image" src="https://github.com/user-attachments/assets/948f472b-76b5-4941-8d4c-b06cf7b783cf" />
<img width="724" height="459" alt="image" src="https://github.com/user-attachments/assets/9cab5d1c-6de6-4d41-b6cf-7844890f1ae3" />

```
df.boxplot(column="Age",by="Survived")
```

<img width="704" height="467" alt="image" src="https://github.com/user-attachments/assets/4532aad3-b6d2-4d3b-bb70-7ff32ac321e4" />

```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```

<img width="847" height="477" alt="image" src="https://github.com/user-attachments/assets/72ed2622-dad4-414c-8e7e-539ada27c286" />

```
fig, axl=plt.subplots(figsize=(8,5))
plt=sns.boxplot(ax=axl,x='Pclass',y='Age',hue='Gender',data=df)

```

<img width="850" height="436" alt="image" src="https://github.com/user-attachments/assets/e7221513-3484-4931-ba03-75ff8c9f41a5" />

```
 plt=sns.boxplot(x='Pclass',y='Age',hue='Gender',data=df)
```

<img width="703" height="466" alt="image" src="https://github.com/user-attachments/assets/8aa8f921-ba6d-4e42-8803-e4a321dea91c" />


```

import seaborn as sns
sns.catplot(x='Pclass',y="Age",hue="Gender",col="Survived",kind="box",data=df)

```

<img width="1233" height="467" alt="image" src="https://github.com/user-attachments/assets/3ce57fba-cc54-452c-b8cf-33ea836fcbfb" />

```
sns.catplot(data=df,col="Survived",x="Gender",hue='Pclass',kind="count")
```

<img width="1297" height="437" alt="image" src="https://github.com/user-attachments/assets/88b34187-fca1-4888-b9a9-82f5ddb20051" />
<img width="1297" height="437" alt="image" src="https://github.com/user-attachments/assets/2015dc08-5898-4b16-9244-7052f5cbfbc5" />

```
corr=df.corr(numeric_only=True)
sns.heatmap(corr,annot=True)
```

<img width="610" height="413" alt="image" src="https://github.com/user-attachments/assets/36a0014b-d3e3-4ac9-8145-c7f73402cf97" />

```

corr=df.select_dtypes(include=np.number).corr()
sns.heatmap(corr,annot=True)

```

<img width="611" height="416" alt="image" src="https://github.com/user-attachments/assets/336a76b2-0311-4bd4-9936-b8424a42a273" />

# RESULT
       
 Thus the programs are executed successfully.
