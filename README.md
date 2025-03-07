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


            <<include your coding and its corressponding output screen shots here>>
# Result
          <<include your Result here>>
