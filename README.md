# Ex-07-Data-Visualization-

## AIM
To Perform Data Visualization on the given dataset and save the data to a file. 

# Explanation
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

# ALGORITHM
### STEP 1
Read the given Data
### STEP 2
Clean the Data Set using Data Cleaning Process
### STEP 3
Apply Feature generation and selection techniques to all the features of the data set
### STEP 4
Apply data visualization techniques to identify the patterns of the data.


# CODE

NAME:KAMALI.E
REGISTER NUMBER:212222110015
## DATA:
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
import seaborn as sbn
df=pd.read_csv("/content/Superstore.csv",encoding='windows-1252')
df.head()

# DATA CLEANING
df.info()

df.isnull().sum()

1.Which Segment has Highest sales?
sbn.barplot(x=df['Segment'],y=df['Sales'])
plt.title("Highest Sales of the segment")

2.Which City has Highest profit?
sbn.barplot(x=df['City'],y=df['Profit'])
plt.title("Highest Profit of cities")

City=df.loc[:,["City","Profit"]]
df.head(5)
City=City.groupby(by=["City"]).sum().sort_values(by="Profit")
plt.figure(figsize=(10,10))
sbn.barplot(x=City.index,y="Profit",data=City)
plt.xticks(rotation = 90)
plt.xlabel=("City")
plt.ylabel=("Profit")
plt.show()

3.Which ship mode is profitable?
sbn.barplot(x=df['Ship Mode'],y=df['Profit'])
plt.title("Profitable Ship Mode")

4.Sales of the product based on region.
sbn.barplot(x=df['Sales'], y=df['Region'])
plt.title("Sales of Product based on Region")

5.Find the relation between sales and profit.
sbn.lineplot(x=df['Sales'], y=df['Profit'])
plt.title("Relation between Sales and Profit")

6.Find the relation between sales and profit based on the following category. i) Segment ii)City iii)States iv)Segment and Ship Mode v)Segment, Ship mode and Region

i) Segment
grouped_data = df.groupby('Segment')[['Sales', 'Profit']].mean()
# Create a bar chart of the grouped data
fig, ax = plt.subplots()
ax.bar(grouped_data.index, grouped_data['Sales'], label='Sales')
ax.bar(grouped_data.index, grouped_data['Profit'], bottom=grouped_data['Sales'], label='Profit')
ax.set_xlabel('Segment')
ax.set_ylabel('Value')
ax.legend()
plt.show()

ii) City
grouped_data = df.groupby('City')[['Sales', 'Profit']].mean()
# Create a bar chart of the grouped data
fig, ax = plt.subplots()
ax.bar(grouped_data.index, grouped_data['Sales'], label='Sales')
ax.bar(grouped_data.index, grouped_data['Profit'], bottom=grouped_data['Sales'], label='Profit')
ax.set_xlabel('City')
ax.set_ylabel('Value')
ax.legend()
plt.show()

iii) States
grouped_data = df.groupby('State')[['Sales', 'Profit']].mean()
# Create a bar chart of the grouped data
fig, ax = plt.subplots()
ax.bar(grouped_data.index, grouped_data['Sales'], label='Sales')
ax.bar(grouped_data.index, grouped_data['Profit'], bottom=grouped_data['Sales'], label='Profit')
ax.set_xlabel('State')
ax.set_ylabel('Value')
ax.legend()
plt.show()

iv)Segment and Ship Mode
grouped_data = df.groupby(['Segment', 'Ship Mode'])[['Sales', 'Profit']].mean()
pivot_data = grouped_data.reset_index().pivot(index='Segment', columns='Ship Mode', values=['Sales', 'Profit'])
# Create a bar chart of the grouped data
fig, ax = plt.subplots()
pivot_data.plot(kind='bar', ax=ax)
ax.set_xlabel('Segment')
ax.set_ylabel('Value')
plt.legend(title='Ship Mode')
plt.show()

v)Segment, Ship mode and Region
grouped_data = df.groupby(['Segment', 'Ship Mode','Region'])[['Sales', 'Profit']].mean()
pivot_data = grouped_data.reset_index().pivot(index=['Segment', 'Ship Mode'], columns='Region', values=['Sales', 'Profit'])
sns.set_style("whitegrid")
sns.set_palette("Set1")
pivot_data.plot(kind='bar', stacked=True, figsize=(10, 5))
plt.legend(title='Region')
plt.show()

# OUPUT

![8 1](https://github.com/Kamali22004796/Ex-08-Data-Visualization-/assets/120567837/e81cfd6d-daaf-4341-9e4a-364b055a570a)

![8 2](https://github.com/Kamali22004796/Ex-08-Data-Visualization-/assets/120567837/bf0abd28-8561-4bb4-b4f9-65aee82d77d3)

![8 3](https://github.com/Kamali22004796/Ex-08-Data-Visualization-/assets/120567837/3fce1e40-fb9b-44a9-99fa-75c5b569a7ec)

![8 4](https://github.com/Kamali22004796/Ex-08-Data-Visualization-/assets/120567837/1ffa3a9c-b37c-4965-818e-6b03740eab62)

![8 5](https://github.com/Kamali22004796/Ex-08-Data-Visualization-/assets/120567837/b5de94d1-93d4-4c2f-bdd8-c84eb1fb4249)

![8 6](https://github.com/Kamali22004796/Ex-08-Data-Visualization-/assets/120567837/bd9623f0-41dc-4d5d-a87c-149b88ada969)

![8 7](https://github.com/Kamali22004796/Ex-08-Data-Visualization-/assets/120567837/26f6e617-0f3b-4d4a-b623-8b8743117f7b)

![8 8](https://github.com/Kamali22004796/Ex-08-Data-Visualization-/assets/120567837/d53d0b4c-2960-4f7b-a907-69807c86ad2e)

![8 9](https://github.com/Kamali22004796/Ex-08-Data-Visualization-/assets/120567837/16168ef9-0fe4-4352-95dd-7a5df75594ee)

![8 10](https://github.com/Kamali22004796/Ex-08-Data-Visualization-/assets/120567837/ccf02752-1d6f-44ac-bda2-e7d122c864be)

![8 11](https://github.com/Kamali22004796/Ex-08-Data-Visualization-/assets/120567837/b276ed7a-6bce-4906-a0d4-4a484d10a005)

![8 12](https://github.com/Kamali22004796/Ex-08-Data-Visualization-/assets/120567837/7a49de59-c1a1-4219-86c0-0ebef15cb9c0)

##RESULT

Hence the data visualization method for the given dataset applied successfully.






















