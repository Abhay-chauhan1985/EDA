# EDA1
Data Visualization
#importing libraries
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
%matplotlib inline
#uploading the data
train=pd.read_csv('titanic_train.csv')
train.head()
sns.set_style('whitegrid')
sns.countplot(x='Survived',data=train)
>>>![image](https://user-images.githubusercontent.com/77687280/118947174-b4776300-b974-11eb-9693-aa7bdc83663b.png)
#we can see more than 500 people,who can not survive.

sns.set_style('whitegrid')
sns.countplot(x='Survived',hue='Sex',data=train,palette='RdBu_r')
>>>![image](https://user-images.githubusercontent.com/77687280/118947473-fdc7b280-b974-11eb-9094-7cbf7669e1c4.png)
#we can see that females have survived than male.
#Now we wish to check that how many passengers survived in each class
sns.set_style('whitegrid')
sns.countplot(x='Survived',hue='Pclass',data=train,palette='rainbow')
>>>![image](https://user-images.githubusercontent.com/77687280/118947771-4a12f280-b975-11eb-9eba-03456958d748.png)
#Now we can see that passengers in class 3 are worst survivor where as passengers in 1st class are survived best.
#Now i wish to see the age distribution of survivor.
sns.distplot(train['Age'],kde=False,color='darkred',bins=40)
#distplot>>it gives histogram in kde form
![image](https://user-images.githubusercontent.com/77687280/118948192-ac6bf300-b975-11eb-991b-f6d51e9629ed.png)
#we can see maximum people who survived are in the age group of 20-30.
#siblings and spouse
sns.countplot(x='SibSp',data=train)
>>>![image](https://user-images.githubusercontent.com/77687280/118949030-7aa75c00-b976-11eb-836e-1e0d932ccd51.png)
#We can see maximum people who were travelling ,were alone
#average fare
train['Fare'].hist(color='green',bins=40,figsize=(8,4))
>>>![image](https://user-images.githubusercontent.com/77687280/118949288-b04c4500-b976-11eb-81c0-f8a99f181feb.png)
#Average fare was on between 0-100.


