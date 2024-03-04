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
```python
import pandas as pd
df=pd.read_csv("/content/SAMPLEIDS.csv")
df
```
![image](https://github.com/KesavDeepak/exno1/assets/139336019/20597f67-dec8-4430-9633-d8129ef79a4b)
```python
print(df.head(7))
```
![image](https://github.com/KesavDeepak/exno1/assets/139336019/8bf109cf-1e46-4c59-ae3b-42542cfc6a88)
```python
print(df.tail(2))
```
![image](https://github.com/KesavDeepak/exno1/assets/139336019/1f3e1fa8-e5a6-406b-8eb3-f7ee4e01565a)
```python 
df.info()
 ```

![image](https://github.com/KesavDeepak/exno1/assets/139336019/f328f3bd-b5a6-4a19-ba88-4b5a09e2df5a)
```python
print(df.describe())
```
![image](https://github.com/KesavDeepak/exno1/assets/139336019/366dbacd-315e-4c72-bf8b-fb765f103d93)
```python
df.isnull().sum()
```
![image](https://github.com/KesavDeepak/exno1/assets/139336019/c02f259e-8e54-42fb-95f1-7f3a968da0db)
```python
df.nunique()
```
![image](https://github.com/KesavDeepak/exno1/assets/139336019/b986e2dd-300a-4d69-9890-054b270bdadc)
```python
mn=df.TOTAL.mean()
mn
```
![image](https://github.com/KesavDeepak/exno1/assets/139336019/ee7a1a5c-8519-4cee-b91c-cfe43127d966)
```python
df.TOTAL.fillna(mn,inplace=True)
df
```
![image](https://github.com/KesavDeepak/exno1/assets/139336019/7c39095d-1166-4732-8206-4b53601434e1)
```python
import pandas as pd
import seaborn as sns
age=[1,3,28,27,25,92,30,39,40,50,26,24,29,94]
af=pd.DataFrame(age)
af
```
![image](https://github.com/KesavDeepak/exno1/assets/139336019/4c567418-5f19-4748-928b-5d5c2336fd84)
```python
sns.boxplot(data=af)
```
![image](https://github.com/KesavDeepak/exno1/assets/139336019/083d0ca3-d635-4fdc-8eec-b51ee29b858c)
```python
sns.scatterplot(data=af)
```
![image](https://github.com/KesavDeepak/exno1/assets/139336019/f7e96a8d-d451-40e9-9dfa-58f297de8531)
```python
q1=af.quantile(0.25)
q2=af.quantile(0.50)
q3=af.quantile(0.75)
iqr=q3-q1
iqr
low=q1-1.5*iqr
low
high=q3+1.5*iqr
high
```
![image](https://github.com/KesavDeepak/exno1/assets/139336019/2c9231bc-1d18-4508-b82e-8b0fb54cdfb7)
```python
af=af[((af>=low)&(af<=high))]
af
```

![image](https://github.com/KesavDeepak/exno1/assets/139336019/222a0230-2a34-4959-8665-2d57232e440f)
```python
af.dropna()
```
![image](https://github.com/KesavDeepak/exno1/assets/139336019/1a58622a-2367-4795-968b-3daa6a1aca6f)

```python
sns.boxplot(data=af)
```
![image](https://github.com/KesavDeepak/exno1/assets/139336019/bef4a840-4483-402e-a66e-6888508f9740)
```python
sns.scatterplot(data=af)
```
![image](https://github.com/KesavDeepak/exno1/assets/139336019/2b27a0e8-8cae-4324-b384-88f70a0ce135)
```python
data=[1,12,15,18,21,24,27,30,33,36,39,42,45,48,51,54,57,60,63,66,69,72,75,78,81,84,87,90,93,96,99,102,105]
df=pd.DataFrame(data)
df
```
![image](https://github.com/KesavDeepak/exno1/assets/139336019/95a38ec8-d9ec-4171-9d51-de1579febddc)
```python
import numpy as np
from scipy import stats
z=np.abs(stats.zscore(df))
z
```
![image](https://github.com/KesavDeepak/exno1/assets/139336019/1c7ca638-9d14-4ebd-8538-71087a2a6c30)



# Result
Thus the given program executed successfully.        
