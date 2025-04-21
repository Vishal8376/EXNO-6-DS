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
```
import seaborn as sns
import matplotlib.pyplot as plt
x=[1,2,3,4,5]
y=[3,6,2,7,1]
sns.lineplot(x=x,y=y)
```
![download (16)](https://github.com/user-attachments/assets/1b846a30-2d15-48d6-9921-69e281060886)
```
df=sns.load_dataset("tips")
df
```
![Screenshot 2025-04-21 082231](https://github.com/user-attachments/assets/ab23aeb6-1fe5-47dc-ad54-1c281206cf74)
```
sns.lineplot(x="total_bill",y="tip",data=df,hue="sex",linestyle="solid",legend="auto")
```
![download (17)](https://github.com/user-attachments/assets/a19d4034-48bc-4ee7-b861-5f9e31404029)

```
x=[1,2,3,4,5]
y1=[3,5,2,6,1]
y2=[1,6,4,3,8]
y3=[5,2,7,1,4]
sns.lineplot(x=x,y=y1)
sns.lineplot(x=x,y=y2)
sns.lineplot(x=x,y=y3)
plt.title("Multi-Line Plot")
plt.xlabel('X Label')
plt.ylabel('Y Label')
```
![download (18)](https://github.com/user-attachments/assets/928072ec-fcd2-46f0-857c-3366f2f4070e)

```
tips=sns.load_dataset("tips")
avg_total_bill=tips.groupby("day")["total_bill"].mean()
avg_tip=tips.groupby("day")["tip"].mean()
plt.figure(figsize=(8,6))
p1=plt.bar(avg_total_bill.index,avg_total_bill,label="Total Bill")
p2=plt.bar(avg_tip.index,avg_tip,bottom=avg_total_bill,label="Tip")
plt.xlabel("Day of the Week")
plt.ylabel("Amount")
plt.title("Average Total Bill and Tip by Day")
plt.legend()
```
![download (19)](https://github.com/user-attachments/assets/e6252c0f-bc3d-47cd-bb64-e6d99f3a622e)
```
avg_total_bill=tips.groupby("time")["total_bill"].mean()
avg_tip=tips.groupby("time")["tip"].mean()
p1=plt.bar(avg_total_bill.index,avg_total_bill,label="Total Bill",width=0.4)
p2=plt.bar(avg_tip.index,avg_tip,bottom=avg_total_bill,label="Tip",width=0.4)
plt.xlabel("Day of the Week")
plt.ylabel("Amount")
plt.title("Average Total Bill and Tip by Day")
plt.legend()
```
![download (20)](https://github.com/user-attachments/assets/71bd32fd-db31-4f2e-a95f-0f6252ea7575)
```
years=range(2000,2012)
apples=[0.895,0.91,0.919,0.926,0.929,0.931,0.934,0.936,0.937,0.9375,0.9372,0.939]
oranges=[0.962,0.941,0.930,0.923,0.918,0.908,0.907,0.904,0.901,0.898,0.9,0.896]
plt.bar(years,apples)
plt.bar(years,oranges,bottom=apples)
```
![download (21)](https://github.com/user-attachments/assets/0e170e8d-c506-4a7a-a0a7-1f5e0bd52b34)
```
sns.barplot(x="day",y="total_bill",data=df,hue="sex",palette="Set1")
plt.xlabel("Day of the Week")
plt.ylabel("Total Bill")
plt.title("Total Bill by Day and Gender")
```
![download (22)](https://github.com/user-attachments/assets/75f562b0-bd25-42d1-9985-69f28afc56e6)
```
import pandas as pd
dt=pd.read_csv("/content/titanic_dataset.csv")
dt
```
![image](https://github.com/user-attachments/assets/e60ed752-71c4-407b-b326-7766f0e251a7)
```
plt.figure(figsize=(8,5))
sns.barplot(x="Embarked",y="Fare",data=dt,palette='rainbow')
plt.title("Fare of Passenger by Embarked Town")
plt.xlabel("Embarked")
plt.ylabel("Fare")
```
![download (23)](https://github.com/user-attachments/assets/8e20bd16-18a9-4b1a-897f-9792ff4f54d6)
```
plt.figure(figsize=(8,5))
sns.barplot(x="Embarked",y="Fare",data=dt,palette='rainbow',hue="Pclass")
plt.title("Fare of Passenger by Embarked Town,Divided by Class")
plt.xlabel("Embarked")
plt.ylabel("Fare")
```
![download (24)](https://github.com/user-attachments/assets/a72e9ff1-7495-44fb-9269-e463a172abbe)
```
sns.scatterplot(x="total_bill",y="tip",data=df,hue="sex")
plt.xlabel("Total Bill")
plt.ylabel("Tip")
plt.title("Scatter Plot of Total Bill vs Tip Amount")
```
![download (25)](https://github.com/user-attachments/assets/fe097d79-9cfc-4365-8cdb-487363684623)
```
import numpy as np
np.random.seed(1)
num_var=np.random.randn(1000)
num_var=pd.Series(num_var,name="Numerical Variable")
num_var
```
![image](https://github.com/user-attachments/assets/55a55661-3c81-4823-8a3f-c33c6e891634)
```
sns.histplot(data=num_var,kde=True)
```
![download (26)](https://github.com/user-attachments/assets/fd606678-110a-4aaf-bb3e-710c08972421)
```
dt=pd.read_csv("/content/titanic_dataset.csv")
dt
```
![image](https://github.com/user-attachments/assets/eedf8f1a-bc9f-4448-b5be-135370d3c296)
```
sns.histplot(data=dt,x="Pclass",hue="Survived",kde=True)
```
![download (27)](https://github.com/user-attachments/assets/0ec51bb2-0b0e-47ef-aa26-a6b2811bfa1b)
```
np.random.seed(0)
marks=np.random.normal(loc=70,scale=10,size=100)
marks=pd.Series(marks,name="Marks")
marks
```
![image](https://github.com/user-attachments/assets/1a210190-7e13-4e69-a274-69790072ffb8)
```
sns.histplot(data=marks,kde=True,stat='count',cumulative=False,multiple='stack',element='bars',palette='set1',shrink=0.7)
```
![download (28)](https://github.com/user-attachments/assets/b252cf61-7b0c-4718-ba6a-8f83bdf6391b)
```
tips=sns.load_dataset("tips")
sns.boxplot(x=tips['day'],y=tips['total_bill'],hue=tips['sex'])
```
![download (29)](https://github.com/user-attachments/assets/0dfb336e-c0ac-400f-8ad3-7449f93a62ca)
```
sns.boxplot(x='day',y='total_bill',data=tips,hue='smoker',linewidth=2,width=0.6,boxprops={"facecolor":"lightblue","edgecolor":"darkblue"},whiskerprops={"color":"black","linestyle":"--","linewidth":"1.5"},capprops={"color":"black","linestyle":"--","linewidth":1.5})
```
![download (30)](https://github.com/user-attachments/assets/74c5c395-5255-45af-9457-28d471513b3a)
```
sns.boxplot(x="Pclass",y="Age",data=dt,palette='rainbow')
plt.title("Age by Passenger class,Titanic")
```
![download (31)](https://github.com/user-attachments/assets/fe138049-a540-4cf4-b464-0510c1d79d1d)
```
sns.violinplot(x="day",y="total_bill",data=df,hue="smoker",linewidth=2,width=0.6,palette="Set3",inner="quartile")
plt.xlabel("Day of the Week")
plt.ylabel("Total Bill")
plt.title("Violin Plot of Total Bill by Day and Smoker Status")
```
![download (32)](https://github.com/user-attachments/assets/989de65a-775b-48da-ae5f-521611413220)
```
sns.set(style='whitegrid')
tip=sns.load_dataset("tips")
sns.violinplot(x='day',y='tip',data=tip)
```
![download (33)](https://github.com/user-attachments/assets/2bb98445-3e39-487d-9e15-7679ccbfb841)
```
sns.violinplot(x=tip["total_bill"])
```
![download (34)](https://github.com/user-attachments/assets/45247e9f-f3b9-41dd-8df3-8262132c8ff4)
```
sns.violinplot(x='tip',y='day',data=tip)
```
![download (35)](https://github.com/user-attachments/assets/078dcf9b-10ec-4c29-b4b1-a33031d66ddb)
```
sns.kdeplot(data=tips,x='total_bill',hue='time',multiple='fill',linewidth=3,palette='Set2',alpha=0.8)
```
![download (36)](https://github.com/user-attachments/assets/9e0f8ed1-e35f-4988-bf4a-5d7d467d0ec8)
```
sns.kdeplot(data=tips,x='total_bill',hue='time',multiple='stack',linewidth=3,palette='Set2',alpha=0.8)
```
![image](https://github.com/user-attachments/assets/74c28135-6077-4bb4-b4a1-b3b4ccf8c680)
```
sns.kdeplot(data=tips,x='total_bill',hue='time',multiple='layer',linewidth=3,palette='Set2',alpha=0.8)
```
![image](https://github.com/user-attachments/assets/85141ef7-d089-4818-8be0-982752d458d3)
```
data=np.random.randint(low=1,high=100,size=(10,10))
print("The data to be plotted:\n")
print(data)
```
![image](https://github.com/user-attachments/assets/f50485f2-bad1-463f-9445-3d8571d9091e)
```
hm=sns.heatmap(data=data,annot=True)
```
![image](https://github.com/user-attachments/assets/01ba6088-a5b8-47d5-b937-e143378783e1)
```
hm=sns.heatmap(data=data)
```
![image](https://github.com/user-attachments/assets/d431db31-b90a-46f2-be31-7f31095e3ec4)
```
tips=sns.load_dataset("tips")
numeric_cols=tips.select_dtypes(include=np.number).columns
corr=tips[numeric_cols].corr()
sns.heatmap(data=corr,annot=True,cmap='plasma',linewidth=0.5)
```
![image](https://github.com/user-attachments/assets/673a5dd8-9ba8-48da-b81c-06ad3f3313d5)


# Result:
 Include your result here
