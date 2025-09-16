# EXNO: 2 DS
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
df=pd.read_csv("titanic_dataset.csv")
df
```


<img width="1289" height="349" alt="image" src="https://github.com/user-attachments/assets/b68e9457-4ee0-4dfe-84a0-cf6f50a4a7a6" />

```
df.info()
```

<img width="427" height="417" alt="image" src="https://github.com/user-attachments/assets/0081dc1e-7786-4871-b29c-e0d6e030cee8" />

```
df.describe()
```

<img width="791" height="353" alt="image" src="https://github.com/user-attachments/assets/ec7b09af-e8d5-4985-902c-5d19d22d7975" />


```
df.dtypes
```

<img width="245" height="272" alt="image" src="https://github.com/user-attachments/assets/faf94e1b-d893-47f5-9b25-953a31cffba7" />

```
df['Age'].value_counts()
```

<img width="394" height="282" alt="image" src="https://github.com/user-attachments/assets/7faafc76-be51-436e-83f9-146f8c9edcee" />

```
df.shape
```

<img width="121" height="49" alt="image" src="https://github.com/user-attachments/assets/af3347d4-e50d-4e4b-a4a4-d6540c6dc9df" />

```
df.set_index("PassengerId",inplace=True)
df.describe()
```

<img width="670" height="355" alt="image" src="https://github.com/user-attachments/assets/9680d4bf-773c-40a6-9e4f-722f573fddee" />

```
df.nunique
```

<img width="667" height="272" alt="image" src="https://github.com/user-attachments/assets/8efee70f-4bc6-451f-9ed8-e4628a916fe7" />

```
sns.countplot(data=df,x="Survived")
```
<img width="757" height="580" alt="image" src="https://github.com/user-attachments/assets/d919d2ff-0adf-45b2-bc17-8ef811fdc27b" />

```
df.Pclass.unique()
```

<img width="296" height="51" alt="image" src="https://github.com/user-attachments/assets/1dc3d651-f840-4bbc-b910-954fe2934877" />

```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```

<img width="1268" height="288" alt="image" src="https://github.com/user-attachments/assets/3fad72ab-4cd0-4145-b2c4-b0e60f3e6604" />


```
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
```

<img width="943" height="650" alt="image" src="https://github.com/user-attachments/assets/455c114e-29a0-4399-a8a5-4466818f9fc3" />

```
df.boxplot(column="Age",by="Survived")
```

<img width="733" height="630" alt="image" src="https://github.com/user-attachments/assets/f6a0ce60-ca03-409e-af89-c63dc60fe86f" />

```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```

<img width="768" height="576" alt="image" src="https://github.com/user-attachments/assets/f66c8fa4-71bc-4f1d-8100-a0e35f75d272" />

```
fig, ax1=plt.subplots(figsize=(8,5))
plt=sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
```

<img width="895" height="564" alt="image" src="https://github.com/user-attachments/assets/ee32cefd-c8cc-4011-bda6-d0327a66c138" />

```
plt=sns.boxplot(x='Pclass',y='Age',hue='Gender',data=df)
```

<img width="729" height="549" alt="image" src="https://github.com/user-attachments/assets/3baf9437-610a-4b3f-a1a5-29520577c371" />

```
import seaborn as sns
sns.catplot(x="Pclass",y="Age",hue="Gender",col="Survived",kind="box",data=df)
```

<img width="1370" height="661" alt="image" src="https://github.com/user-attachments/assets/e453a408-9fc8-4cab-ae2d-be25c2267808" />

```
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```

<img width="1343" height="645" alt="image" src="https://github.com/user-attachments/assets/4479e49d-4166-4695-beb7-85d435d0215b" />

```
corr=df.select_dtypes(include=np.number).corr()
sns.heatmap(corr,annot=True)
```

<img width="694" height="558" alt="image" src="https://github.com/user-attachments/assets/7d0ff9fe-6f26-43f1-b794-c422607b383f" />




# RESULT

Thus the data analysis has been implemented succesfully.

