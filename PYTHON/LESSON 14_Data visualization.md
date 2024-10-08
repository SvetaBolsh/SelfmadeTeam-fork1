# HOMEWORK
## EASY
- Task 1: Create a bar chart that shows the count of transactions for each unique value in the 'Gender' column (including NaN values). 

VERSION 1:

```py
import pandas as pd
import matplotlib.pyplot as plt

dataset = pd.read_csv('/content/transaction_dataset.csv')

gender_counts = dataset["Gender"].value_counts(dropna=False)
df_gender_counts = pd.DataFrame({'Gender': gender_counts.index.astype(str), 'Count': gender_counts.values})

plt.bar(df_gender_counts["Gender"], df_gender_counts["Count"], color=["pink", "skyblue", "gray"])

plt.title("Count of Customers by Gender")
plt.xlabel("Gender")
plt.ylabel("Count of Customers")

plt.show()
```

![Unknown](https://github.com/user-attachments/assets/e7d3e5e1-14b4-4777-92db-1d8d5f53b27c)

VERSION 2:
```py
import pandas as pd
import matplotlib.pyplot as plt

data = {
    'TransactionID': [1, 2, 3, 4, 5, 6, 7, 8, 9, 10],
    'Gender': ['Male', 'Female', 'Female', 'Male', None, 'Male', 'Female', None, 'Female', 'Male']
}
df = pd.DataFrame(data)

gender_counts = df['Gender'].value_counts(dropna=False)

plt.figure(figsize=(10, 6))
gender_counts.plot(kind='bar', color=['skyblue', 'salmon', 'gray'])

plt.xlabel('Gender')
plt.ylabel('Count of Transactions')
plt.title('Count of Transactions for Each Gender')

plt.xticks(rotation=0)
plt.show()
```
![Unknown](https://github.com/user-attachments/assets/81941778-69a9-4c8b-ba05-b67974f958e6)


### MEDIUM
- Task 2: Create a horizontal bar chart that shows the top 5 most frequent names in the DataFrame, based on the 'name' column. (First, create a grouped DataFrame (name_df), then filter it using iloc, and finally create the visualization.)

```py
import pandas as pd
import matplotlib.pyplot as plt

dataset = pd.read_csv("/content/transaction_dataset.csv")

name_df = dataset['Name'].value_counts()

top_5_names = name_df.iloc[:5]

df_top_5_names = pd.DataFrame({'Names': top_5_names.index, 'Count': top_5_names.values})

plt.barh(df_top_5_names["Names"], df_top_5_names["Count"], color=["blue", "skyblue", "lightgrey", "darkgrey", "black"], edgecolor="black")

plt.title("Top 5 Most Frequent Names")
plt.xlabel("Count")
plt.ylabel("Name")

plt.show()
```
![Unknown-2](https://github.com/user-attachments/assets/14042a19-59d5-48d3-aea7-2a32315a1d00)



### HARD
- Task 3: Create a filtered DataFrame that includes Category == 'Clothing' and Gender == 'M'. How many rows are there in this filtered DataFrame? Format the result as follows: The filtered DataFrame has XXXX rows

```py
import pandas as pd
import matplotlib.pyplot as plt

dataset = pd.read_csv("/content/transaction_dataset.csv")

df = pd.DataFrame(dataset)

filtered_df = dataset[(dataset['Gender'] == 'M') & (dataset['Category'] == 'Clothing')]

fitered_data_rows = filtered_df.shape[0]

print(f"The filtered DataFrame has {fitered_data_rows} rows.")
```
