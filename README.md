# Simple-Linear-Regression
import pandas
import os
from sklearn.linear_model import LinearRegression
from sklearn.model_selection import train_test_split
dataset=pandas.read_csv('SalaryData.csv')
#print(dataset)
x=dataset[['YearsExperience']]
y=dataset['Salary']
model=LinearRegression()
x_train,x_test,y_train,y_test=train_test_split(x,y,test_size=0.30)
model.fit(x_train,y_train)
print("\ncoefficient is =",model.coef_)
y_pred=model.predict(x_test)
eff=0
while True:
	print("enter a to exit")
	i=input("enter experience")
	if i=='a':
		os.system(exit())
	else:
		ex=float(i)
		print("\npredicted value",model.predict([[ex]]))
