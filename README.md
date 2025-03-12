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
# Handling null values
```
import pandas as pd

df=pd.read_csv(r"C:\Users\Suriya\Downloads\Data_set (1).csv")

df
```
![Screenshot 2025-03-07 161615](https://github.com/user-attachments/assets/9fad49da-8d90-4acc-b34a-45f76896e269)


```
df.isnull().sum()
```

![Screenshot 2025-03-07 161641](https://github.com/user-attachments/assets/1d9eddb9-ef17-43ea-b30e-0f2c18320d63)

```
df.isnull().any()
```
![Screenshot 2025-03-07 161648](https://github.com/user-attachments/assets/8f68870d-5c6d-41f0-b34c-9c111477ce7c)


```
df.dropna()
```
![Screenshot 2025-03-07 161701](https://github.com/user-attachments/assets/87353643-c8ae-4806-8f98-c55bd561fa09)


```
f.fillna(0)
```

![Screenshot 2025-03-07 161712](https://github.com/user-attachments/assets/92ce54c8-0447-441b-871d-7cf16ac40b6c)


```
df.fillna(method = 'ffill')
```

![Screenshot 2025-03-07 161726](https://github.com/user-attachments/assets/77e45662-6e44-4a44-b78e-866aa37f8331)


```
df.fillna(method = 'bfill')
```

![Screenshot 2025-03-07 161740](https://github.com/user-attachments/assets/39b735d5-3143-4b5f-9528-b0299d13119e)


```
df_dropped=df.dropna()
df_dropped
```
![Screenshot 2025-03-07 161753](https://github.com/user-attachments/assets/f645139f-c740-407d-add3-f8cee42624d6)


```
df.fillna({"show_name":"breaking bad","country":"america","aired_on":"monday,saturday","original_network":"KBS2","rating":9.6,"current_overall_rank":880.0,"lifetime_popularity_rank":1,"watchers":126795.0})
```

![Screenshot 2025-03-07 161804](https://github.com/user-attachments/assets/c8c082bb-7394-48de-b370-b190804e8014)



# Outliers

```
import pandas as pd
ir=pd.read_csv(r"C:\Users\Suriya\Downloads\iris (1).csv")
ir
```
![Screenshot 2025-03-12 135527](https://github.com/user-attachments/assets/2c9a3093-22d9-4675-9e04-5199303e3d77)


```
ir.describe()
```

![Screenshot 2025-03-12 135535](https://github.com/user-attachments/assets/b7bf04db-d7c2-450d-b23e-55372aa30df9)


```
import seaborn as sns
sns.boxplot(x='sepal_width',data=ir)
```
![Screenshot 2025-03-12 135541](https://github.com/user-attachments/assets/6b44e9f0-bc43-425e-9979-d91cd5d7db1d)



```

 q1=ir.sepal_width.quantile(0.25)
 q3=ir.sepal_width.quantile(0.75)
 iq=q3-q1
 print(iq)
```

![Screenshot 2025-03-12 135550](https://github.com/user-attachments/assets/4988ddea-d01d-4489-973d-547f7410d052)


```
 rid=ir[((ir.sepal_width<(q1-1.5*iq))|(ir.sepal_width>(q3+1.5*iq)))]
 rid['sepal_width']
```
![Screenshot 2025-03-12 135556](https://github.com/user-attachments/assets/bd064582-6021-4024-8b30-27ea4deca1a4)


```
delid=ir[~((ir.sepal_width<(q1-1.5*iq))|(ir.sepal_width>(q3+1.5*iq)))]
delid
```

![Screenshot 2025-03-12 135603](https://github.com/user-attachments/assets/bdab787b-a2d7-40ea-8d5b-e056f3273ebd)


```
sns.boxplot(x='sepal_width',data=delid)


```
![Screenshot 2025-03-12 135609](https://github.com/user-attachments/assets/6d9491cd-1309-4b11-a1bf-299878b8df1f)



```
import matplotlib.pyplot as plt
import numpy as np
import scipy.stats as stats
dataset=pd.read_csv(r"C:\Users\Suriya\Downloads\heights.csv")
dataset

```

![Screenshot 2025-03-12 135616](https://github.com/user-attachments/assets/4dd4c98f-b33b-46e4-83e4-2d5368aeddc6)

```
q1 = dataset['height'].quantile(0.25)
q2 = dataset['height'].quantile(0.5)
q3 = dataset['height'].quantile(0.75)
iqr = q3-q1
iqr

```
![Screenshot 2025-03-12 135623](https://github.com/user-attachments/assets/da2b43da-3102-4638-9333-84d4ec86f068)



```
low = q1- 1.5*iqr
low


```

![Screenshot 2025-03-12 135629](https://github.com/user-attachments/assets/aee6bcf3-e614-4830-bfda-96b81d944294)

```
high = q3 + 1.5*iqr
high

```

![Screenshot 2025-03-12 135633](https://github.com/user-attachments/assets/5d5da814-64ac-4aac-a60a-7ac7f847e634)



```
df1 = dataset[((dataset['height'] >=low)& (dataset['height'] <=high))]
df1
```

![Screenshot 2025-03-12 135639](https://github.com/user-attachments/assets/47c3da53-4545-4b85-98ea-64a61c963d78)




```
z = np.abs(stats.zscore(dataset['height']))
z

```


![Screenshot 2025-03-12 135645](https://github.com/user-attachments/assets/3109d922-3c9a-4ac6-8295-71b3bb02a0e0)


```
df1 = dataset[z<3]
df1
```

![Screenshot 2025-03-12 135651](https://github.com/user-attachments/assets/10950a74-04a2-421d-9e89-9302e1c8d0ec)




# Result
The program executed successfully
