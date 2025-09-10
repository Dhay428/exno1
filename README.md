# NAME:S.Dhayalaprabu
# REGNO:212224230065
# Exno:1
Data Cleaning Process

# AIM
To read the given data and perform data cleaning and save the cleaned data to a file.

# Explanation
Data cleaning is the process of preparing data for analysis by removing or modifying data that is incorrect ,incompleted , irrelevant , duplicated or improperly formatted. Data cleaning is not simply about erasing data ,but rather finding a way to maximize datasets accuracy without necessarily deleting the information.

# Algorithm
STEP 1: Read the given Data

STEP 2: Get the information about the data

STEP 3: Remove the null values from the data

STEP 4: Save the Clean data to the file

STEP 5: Remove outliers using IQR

STEP 6: Use zscore of to remove outliers

# Coding and Output
```
import numpy as np
import pandas as pd
data=pd.read_csv("/content/SAMPLEIDS.csv")
data
```

<img width="1022" height="862" alt="image" src="https://github.com/user-attachments/assets/997c538c-6971-4461-a47e-68a17d1b96d2" />

```
data.head(4)
```

<img width="966" height="214" alt="image" src="https://github.com/user-attachments/assets/21ab86d8-ee94-4962-b69c-349eb665b78c" />

```
df.tail(7)
```
<img width="1013" height="323" alt="image" src="https://github.com/user-attachments/assets/21fb74c8-f1b2-4e3f-a2bc-27274b3a470e" />

```
df.isnull()
```
<img width="826" height="859" alt="image" src="https://github.com/user-attachments/assets/5295cd99-1d8e-40d9-8c2b-7f3af7f86a70" />


```
df.isnotnull()
```
<img width="813" height="852" alt="image" src="https://github.com/user-attachments/assets/a0f42e06-38f0-46b8-93b4-5edaa28bca1c" />


```
df.isnull().sum()
```
<img width="196" height="572" alt="image" src="https://github.com/user-attachments/assets/ca7344af-aaef-40d8-8f4d-d812e73d5b4a" />


```
df.isnull().any()
```
<img width="188" height="567" alt="image" src="https://github.com/user-attachments/assets/79c2a5d7-e896-4635-8c50-fb5291594aec" />


```
df.dropna(axis=1)
```
<img width="304" height="871" alt="image" src="https://github.com/user-attachments/assets/54152afd-26c5-494c-a782-1a1250bbf7ab" />

```
data.dropna(axis=0)
```
<img width="1013" height="556" alt="image" src="https://github.com/user-attachments/assets/1b5d1637-c6a1-4115-bd07-f7c750351ace" />


```
df.fillna(0)
```
<img width="1015" height="856" alt="image" src="https://github.com/user-attachments/assets/f2599ce3-81a4-45ee-bef9-437aeb9c92b9" />


```
df.fillna(method='ffill')
```
<img width="1024" height="862" alt="image" src="https://github.com/user-attachments/assets/08190d92-37cc-4f1d-8baf-dc9e367ea265" />

```
data.bfill()
```
<img width="1021" height="849" alt="image" src="https://github.com/user-attachments/assets/ce20730d-304c-40a4-853a-3ba10a4f4ba1" />

```
df.fillna({'GENDER':'MALE','NAME':'SRI'})
```
<img width="1020" height="856" alt="image" src="https://github.com/user-attachments/assets/0a9a9a2b-760f-4f55-9d02-418c89155eb7" />



```
ir=pd.read_csv("/content/iris.csv")
ir
```

<img width="658" height="512" alt="image" src="https://github.com/user-attachments/assets/d1c32c49-5bdf-4bb4-8a97-176ab47f3f99" />


```
ir.describe()
```

<img width="588" height="367" alt="image" src="https://github.com/user-attachments/assets/5f04569c-9617-4346-94d5-fd1bdbfef43c" />



```
import seaborn as sns

sns.boxplot(x='sepal_width',data=ir)

```
<img width="688" height="568" alt="image" src="https://github.com/user-attachments/assets/471ece34-c3bb-443f-a2fb-8c4e8a5610a9" />


```
Q1=ir.sepal_width.quantile(0.25)
Q3=ir.sepal_width.quantile(0.75)
(IQR)=Q3-Q1
print(IQR)
```
<img width="70" height="40" alt="image" src="https://github.com/user-attachments/assets/c693307f-cc1e-4e6b-9182-f8b5569f4599" />


```
ran=ir[((ir.sepal_width<(Q1-1.5*IQR))|(ir.sepal_width>(Q3+1.5*IQR)))]
ran['sepal_width']
```
<img width="196" height="257" alt="image" src="https://github.com/user-attachments/assets/badc9f85-11a1-45a8-9912-3d59d4698cb0" />


```
ran=ir[~((ir.sepal_width<(Q1-1.5*IQR))|(ir.sepal_width>(Q3+1.5*IQR)))]
ran['sepal_width']
```

<img width="656" height="509" alt="image" src="https://github.com/user-attachments/assets/746925f0-8e0d-43b2-accc-a40221010fe7" />


```
rid=ir[((ir.sepal_width>(q1-1.5*iqr))&(ir.sepal_width<(q3+1.5*iqr)))]
rid['sepal_width']
```
<img width="658" height="510" alt="image" src="https://github.com/user-attachments/assets/2064e173-0998-40f8-86ad-215c29bcfc20" />


```
import numpy as np
import scipy.stats as stats
z=np.abs(stats.zscore(ir['petal_length']))
z
```
<img width="690" height="661" alt="image" src="https://github.com/user-attachments/assets/a5c7c25f-48ba-4963-8ca5-4c8ac42f45cb" />


```
ir1=ir[z<3]
ir1
```
<img width="648" height="92" alt="image" src="https://github.com/user-attachments/assets/cd548348-d8e1-4f3f-afad-3482358a120e" />



            
# Result
Thus the program has excecuted successfully.
