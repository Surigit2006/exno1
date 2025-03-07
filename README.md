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
```
df.isnull().sum()
```
```
df.isnull().any()
```
```
df.dropna()
```
```
f.fillna(0)
```
```
df.fillna(method = 'ffill')
```
```
df.fillna(method = 'bfill')
```
```
df_dropped=df.dropna()
df_dropped
```
```
df.fillna({"show_name":"breaking bad","country":"america","aired_on":"monday,saturday","original_network":"KBS2","rating":9.6,"current_overall_rank":880.0,"lifetime_popularity_rank":1,"watchers":126795.0})
```

            <<include your coding and its corressponding output screen shots here>>
# Result
          <<include your Result here>>
