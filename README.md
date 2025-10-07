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
import pandas as pd
df = pd.read_csv("Data_set.csv")
print(df)
```
<img width="1093" height="514" alt="ds1 1" src="https://github.com/user-attachments/assets/c42a1547-69a1-4244-8f98-626a0383c8c8" />
<img width="1091" height="678" alt="ds1 2" src="https://github.com/user-attachments/assets/d96fadce-c9f1-4b2b-877a-9e30a34027ff" />
```
df.describe()
```
<img width="1226" height="439" alt="ds1 3" src="https://github.com/user-attachments/assets/cca498fb-3b89-41fd-99f2-869ac4e85a17" />
```
df.info()
```
<img width="818" height="486" alt="ds1 4" src="https://github.com/user-attachments/assets/cee7ec73-35ec-4149-975c-e23dce5cf097" />
```
df.head(4)
```
<img width="1756" height="393" alt="ds1 5" src="https://github.com/user-attachments/assets/62da64f3-f945-4e9f-8e00-77fa22fcde93" />
```
df.tail(3)
```
<img width="1759" height="348" alt="ds1 6" src="https://github.com/user-attachments/assets/7805abd0-65e3-4bbf-9fda-e48af758b46e" />
```
df.isnull()
```
<img width="1757" height="600" alt="ds1 7" src="https://github.com/user-attachments/assets/29b32806-549c-48c7-aa45-9b99a2fc3037" />
```
df.notnull()
```
<img width="1755" height="586" alt="ds1 8" src="https://github.com/user-attachments/assets/1711bb1b-cd8e-4542-8d52-1ce76c3b882b" />
```
df.isnull().sum()
```
<img width="554" height="586" alt="ds1 9" src="https://github.com/user-attachments/assets/4fdc6239-c077-4a61-9479-1ee65abb047e" />
```
df.notnull().sum()
```
<img width="504" height="577" alt="ds1 10" src="https://github.com/user-attachments/assets/b136722a-38de-46c9-8349-0c79fe5c17bc" />
```
df.shape()
df[df['rating'] > 8]
```
<img width="1849" height="639" alt="ds1 11" src="https://github.com/user-attachments/assets/9b5b3bab-48de-45d8-8f97-b445e51280b9" />
```
df[df['num_episodes'] > 20]
```
<img width="1759" height="547" alt="ds1 12" src="https://github.com/user-attachments/assets/d258a9f8-c482-4e43-8a62-6a3560cc4503" />
```
df.iloc[2:5 , :-3]
```
<img width="1326" height="240" alt="ds1 13" src="https://github.com/user-attachments/assets/bbc7e975-5c32-4617-9066-938a749985b1" />
```
df.iloc[[6,7,8],[1,2,3]]
```
<img width="727" height="224" alt="ds1 14()" src="https://github.com/user-attachments/assets/0f46c6bd-c3de-4890-912a-7865faccb96d" />
```
df.loc[3:5 , ['country' , 'num_episodes']]
```
<img width="502" height="229" alt="ds1 14" src="https://github.com/user-attachments/assets/1d36df2a-c9e5-444e-ae70-c139cb53d8bf" />
```
df['country'].value_counts()
```
<img width="544" height="327" alt="ds1 15" src="https://github.com/user-attachments/assets/3068a4ef-aec3-4c7b-a984-a73078c81f77" />
```
df.count()
```
<img width="507" height="581" alt="ds1 16" src="https://github.com/user-attachments/assets/352e4d6f-b844-499f-8881-1910bc6c9335" />
```
df.dropna(axis = 1)
```
<img width="824" height="600" alt="ds1 17" src="https://github.com/user-attachments/assets/570e40dc-86ec-4309-a057-bdcc7f1d7729" />
```
df.fillna(0)
```
<img width="1740" height="600" alt="ds1 18" src="https://github.com/user-attachments/assets/ede44748-feb7-4d68-b8d4-e9cb4078ff21" />
```
df.fillna(method = 'bfill')
```
<img width="1747" height="580" alt="ds1 19" src="https://github.com/user-attachments/assets/4f0e786c-4489-4324-a8f3-388118698783" />
```
df.interpolate()
```
<img width="1735" height="579" alt="ds1 21" src="https://github.com/user-attachments/assets/761e16b9-487f-4701-80da-845b3d97820d" />
<img width="1685" height="464" alt="ds1 22" src="https://github.com/user-attachments/assets/44d12fb4-abb4-4507-93dc-cd5e3bb2a1d7" />
```
ffil = df.fillna(method = 'ffill')
print(ffil)
```
<img width="1088" height="561" alt="ds1 23" src="https://github.com/user-attachments/assets/b2f65a2e-f011-43e5-9aa4-0c1972e288f1" />
<img width="1751" height="650" alt="ds1 24" src="https://github.com/user-attachments/assets/c09cf480-7dd2-4098-b46d-ef3edb59f763" />
```
bfil = df.fillna(method = 'bfill')
print(bfil)
```
<img width="1104" height="550" alt="ds1 25" src="https://github.com/user-attachments/assets/d3607637-bfce-4e35-835e-b340f75f7093" />
```
m = df.num_episodes.mean()
print(m)
```
<img width="466" height="186" alt="ds1 27()" src="https://github.com/user-attachments/assets/7b5e1c3e-8aed-486a-bac4-24aa2ad04d36" />
```
m = df.fillna(df['num_episodes'].mean())
print(m)
```
<img width="1151" height="371" alt="ds1 27" src="https://github.com/user-attachments/assets/c235c868-c9f4-4af8-90c5-86eb7ab2d8d4" />
```
fmean = df['lifetime_popularity_rank'].fillna(value=df['lifetime_popularity_rank'].mean())
print(fmean)
```
<img width="1246" height="460" alt="ds1 29" src="https://github.com/user-attachments/assets/d97f5c10-6999-42a0-8a96-53e574952bc7" />
```
df = pd.read_csv('SAMPLEIDS.csv')
print(df)
```

<img width="1115" height="554" alt="ds1 30" src="https://github.com/user-attachments/assets/f5f18e24-d1d6-4f7f-9476-1fe984ffca94" />
<img width="513" height="642" alt="ds1 31" src="https://github.com/user-attachments/assets/2a9431d3-e232-4a90-add7-070822102b08" />
```
df['GENDER'].value_counts()
```
<img width="648" height="285" alt="ds1 32" src="https://github.com/user-attachments/assets/e7684260-74a5-45e8-b625-53e1902e33c7" />
```
x1 = df.dropna(how='any')
print(x1)
```
<img width="1232" height="577" alt="ds1 33" src="https://github.com/user-attachments/assets/96f036b4-1a62-4975-96b3-a58218360685" />
<img width="1076" height="505" alt="ds1 34" src="https://github.com/user-attachments/assets/1034985f-dff6-4982-945c-e03e9168b215" />
```
res = df.dropna(subset=['M1','M2','M3','M4'],how='any')
print(res)
```
<img width="1113" height="591" alt="ds1 35" src="https://github.com/user-attachments/assets/49f24854-ab26-416d-928b-944b68dca89a" />
<img width="1051" height="571" alt="ds1 36" src="https://github.com/user-attachments/assets/9ef43205-1ace-43f6-8158-5e54a7e88aa2" />
```
df=pd.read_csv('heights.csv')
print(df)
```
<img width="595" height="561" alt="ds1 37" src="https://github.com/user-attachments/assets/9c6b7813-20fd-469c-a706-9a923c7cb765" />
```
import seaborn as sns
import matplotlib.pyplot as plt

sns.boxplot(data=df)
plt.show()
```
<img width="1919" height="860" alt="ds1 39" src="https://github.com/user-attachments/assets/d1786eca-421b-4d93-9fd9-4691eb42073f" />
```
sns.scatterplot(data=df)
```
<img width="1919" height="876" alt="ds1 40" src="https://github.com/user-attachments/assets/9ffefb16-6aa4-46ef-b0a8-d35de487fd2a" />
```
q3 = df["height"].quantile(0.75)
q1 = df["height"].quantile(0.25)
iqr = q3 - q1
print(iqr)
```
<img width="388" height="76" alt="ds1 41()" src="https://github.com/user-attachments/assets/728f6422-8d68-4f11-b444-9a1ad79b4fc4" />
```
q1, q3 = df["height"].quantile([0.25, 0.75])
iqr = q3 - q1
lb, ub = q1 - 1.5*iqr, q3 + 1.5*iqr
outliers = df[(df["height"] < lb) | (df["height"] > ub)]

print(f"Lower bound: {lb}\nUpper bound: {ub}\nOutliers:\n{outliers}")
```
<img width="474" height="201" alt="ds1 41" src="https://github.com/user-attachments/assets/491e97f8-44ee-493b-9625-c8234593303b" />
```
import numpy as np
from scipy import stats

z = np.abs(stats.zscore(df["height"]))
z = pd.Series(z, name="height")   # make it a Series with name
print(z)
```
<img width="457" height="452" alt="ds1 42" src="https://github.com/user-attachments/assets/d6689c00-e5b3-4bb3-b189-858023baf3a9" />
```
df1 = df[z<3]
print(df1)
```

<img width="430" height="426" alt="ds1 43" src="https://github.com/user-attachments/assets/9cbaa27b-7008-4bfb-9f76-d06a772290eb" />


# Result
      Hence the data has clened successfully and saved in a file.    
