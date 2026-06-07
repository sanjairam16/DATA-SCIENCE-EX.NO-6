# EXNO-6-DS-DATA VISUALIZATION USING SEABORN LIBRARY

# Aim:
  To Perform Data Visualization using seaborn python library for the given datas.

# EXPLANATION:
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

# Algorithm:
STEP 1:Include the necessary Library.

STEP 2:Read the given Data.

STEP 3:Apply data visualization techniques to identify the patterns of the data.

STEP 4:Apply the various data visualization tools wherever necessary.

STEP 5:Include Necessary parameters in each functions.

# Coding and Output:
~~~
import seaborn as sns
import matplotlib.pyplot as plt
import pandas as pd
import numpy as np
x = [1, 2, 3, 4, 5]
y = [3, 6, 2, 7, 1]
sns.lineplot(x=x,y=y)
~~~

<img width="811" height="608" alt="e6-1" src="https://github.com/user-attachments/assets/29a6fdd3-3a59-46eb-848f-258547268c60" />

~~~
df = sns.load_dataset("tips")
df
~~~

<img width="722" height="585" alt="e6-2" src="https://github.com/user-attachments/assets/8443825a-a07e-4146-a277-1d6aa4d0ccc4" />

~~~
sns.lineplot(x="total_bill",y="tip", data=df, hue="sex", linestyle='solid', legend="auto")
~~~

<img width="830" height="619" alt="e6-3" src="https://github.com/user-attachments/assets/68ff232d-17cd-4e68-90cb-1b7ec2fa227f" />

~~~
x=[1, 2, 3, 4, 5]
y1=[3, 5, 2, 6, 1]
y2=[1, 6, 4, 3, 8]
y3=[5, 2, 7, 1, 4]
sns.lineplot(x=x, y=y1)
sns.lineplot(x=x, y=y2)
sns.lineplot(x=x, y=y3)
plt.title("Multi-Line Plot")
plt.xlabel('X Label')
plt.ylabel("Y Label")
~~~

<img width="824" height="636" alt="e6-4" src="https://github.com/user-attachments/assets/af7dab87-1808-4dda-86b7-f0bc39035235" />

~~~
tips=sns.load_dataset('tips')
avg_total_bill = tips.groupby('day')['total_bill'].mean()
avg_tip = tips.groupby('day')['tip'].mean()
plt.figure(figsize=(8, 6))
p1 = plt.bar(avg_total_bill.index, avg_total_bill, label='Total Bill')
p2 = plt.bar(avg_tip.index, avg_tip, bottom=avg_total_bill, label='Tip')
plt.xlabel('Day of the Week')
plt.ylabel('Amount')
plt.title('Average Total Bill and Tip by Day')
plt.legend()
~~~

<img width="829" height="647" alt="e6-5" src="https://github.com/user-attachments/assets/d2d3bbd1-686e-406f-98d6-730877b7af18" />

~~~
avg_total_bill = tips.groupby('time')['total_bill'].mean() 
avg_tip=tips.groupby('time') ['tip'].mean()
p1= plt.bar(avg_total_bill.index, avg_total_bill, label='Total Bill', width=0.4)
p2 = plt.bar(avg_tip.index,avg_tip,bottom=avg_total_bill,label='Tip', width=0.4)
~~~

<img width="724" height="526" alt="e6-6" src="https://github.com/user-attachments/assets/7b783c66-1bcd-4154-bec7-35a077d6794e" />

~~~
years=range(2000, 2012)
apples=[0.895, 0.91, 0.919, 0.926, 0.929, 0.931, 0.934, 0.936, 0.937, 0.9375, 0.9372, 0.939] 
oranges = [0.962, 0.941, 0.930, 0.923, 0.918, 0.908, 0.907, 0.904, 0.901, 0.898, 0.9, 0.896, ]
plt.bar(years, apples)
plt.bar(years, oranges, bottom=apples)
~~~

<img width="761" height="544" alt="e6-7" src="https://github.com/user-attachments/assets/51b9c147-87b0-48df-b62e-7f1b0f18f924" />

~~~
import seaborn as sns
dt= sns.load_dataset('tips')
sns.barplot(x='day', y='total_bill', hue='sex', data=dt, palette='Set1')
plt.xlabel('Day of the Week')
plt.ylabel("Total Bill")
plt.title('Total Bill by Day and Gender')
~~~

<img width="760" height="609" alt="e6-8" src="https://github.com/user-attachments/assets/a0dfc12b-920c-4fa8-9bf2-bc6ee37d66d2" />

~~~
tit=pd.read_csv("titanic_dataset.csv")
tit
~~~


<img width="832" height="269" alt="e6-9" src="https://github.com/user-attachments/assets/d3a2a71e-b559-4381-8d94-93d69a19182d" />

~~~
plt.figure(figsize=(8,5))
sns.barplot(x='Embarked', y='Fare', data=tit, palette='rainbow', hue='Pclass') 
plt.title("Fare of Passenger by Embarked Town, Divided by Class")
~~~

<img width="833" height="516" alt="e6-10" src="https://github.com/user-attachments/assets/82ca30d5-ae67-49c1-ba19-db547f2e3278" />

~~~
tips=sns.load_dataset('tips')
sns.scatterplot(x='total_bill', y='tip', hue='sex', data=tips)
plt.xlabel('Total Bill')
plt.ylabel("Tip Amount")
plt.title('Scatter Plot of Total Bill vs. Tip Amount')
~~~

<img width="798" height="536" alt="e6-11" src="https://github.com/user-attachments/assets/66f39269-3b64-49e4-a5ee-1f410c45520b" />

~~~
num_var = np.random.randn(1000)
num_var=pd.Series(num_var, name = "Numerical variable")
num_var
~~~

<img width="610" height="249" alt="e6-12" src="https://github.com/user-attachments/assets/07b71b65-f547-4169-9159-b634596c7523" />
~~~
sns.histplot(data = num_var, kde = True)
~~~

<img width="805" height="517" alt="e6-13" src="https://github.com/user-attachments/assets/bda1d474-0183-42e0-bc21-8e3282ee62fc" />

~~~
df=pd.read_csv("titanic_dataset.csv")
sns.histplot(data=df,x="Pclass", hue="Survived", kde=True)
~~~

<img width="810" height="513" alt="e6-14" src="https://github.com/user-attachments/assets/29dd62e5-36ae-4176-a56f-26ad513aa51e" />

~~~
tips=sns.load_dataset('tips')
sns.boxplot(x=tips['day'], y=tips ['total_bill'], hue=tips['sex'])
~~~

<img width="758" height="509" alt="e6-15" src="https://github.com/user-attachments/assets/8cac6047-f50a-4899-ad24-bd0a4965551a" />

~~~
sns.boxplot(x="day", y="total_bill", hue="smoker", data=tips, linewidth=2, width=0.6, boxprops={"facecolor": "lightblue", "edgecolor": "darkblue"},
whiskerprops={"color": "black", "linestyle": "--", "linewidth": 1.5}, capprops={"color": "black", "linestyle": "--", "linewidth": 1.5})
~~~

<img width="786" height="511" alt="e6-16" src="https://github.com/user-attachments/assets/c517cb7c-3151-4530-ac59-352e5fd589e6" />

~~~
sns.violinplot(x="day", y="total_bill", hue="smoker", data=tips, linewidth=2, width=0.6, palette="Set3", inner="quartile")
plt.xlabel("Day of the Week")
plt.ylabel("Total Bill")
plt.title("Violin Plot of Total Bill by Day and Smoker Status")
~~~

<img width="825" height="476" alt="e6-18" src="https://github.com/user-attachments/assets/965ac246-a73b-43a0-bb20-c5da0b6d9e3c" />

~~~
mart=mart[['PassengerId', 'Survived', 'Age', 'Name', 'Ticket', 'Embarked']] 
mart.head(10)
~~~
<img width="826" height="302" alt="e6-19" src="https://github.com/user-attachments/assets/e2b8e6c7-97e5-4ff0-9cda-0d37c1f70ce1" />

~~~
sns.kdeplot(data=mart,x='Age')
~~~
<img width="758" height="509" alt="e6-20" src="https://github.com/user-attachments/assets/73b38ff1-8f0e-4a7c-9abd-67cc04a1c0c6" />

~~~
sns.kdeplot(data=mart,x='PassengerId',hue='Survived',multiple='stack')
~~~


<img width="830" height="489" alt="e6-21" src="https://github.com/user-attachments/assets/61576141-8890-4cd4-b096-c89986d0071e" />
~~~
data = np.random.randint(low = 1, high = 100, size = (10,10))
hm=sns.heatmap(data=data,annot=True)
~~~

<img width="707" height="470" alt="e6-22" src="https://github.com/user-attachments/assets/0b5f5db3-3d5a-4137-b19e-05389f819ccc" />

~~~
hm=sns.heatmap(data=data)
~~~

<img width="679" height="468" alt="e6-23" src="https://github.com/user-attachments/assets/af0181c5-8b56-46cc-8dce-0836c2a84ff3" />


# Result:
Thus, the data visualization techniques of seaborn has been implemented and executed.
