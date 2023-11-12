# Ex:05 Feature Generation
## AIM
To read the given data and perform Feature Generation process and save the data to a file.
## Explanation
Feature Generation (also known as feature construction, feature extraction or feature engineering) is the process of transforming features into new features that better relate to the target.
## ALGORITHM
### STEP 1
Read the given Data
### STEP 2
Clean the Data Set using Data Cleaning Processes
### STEP 3
Apply Feature Generation techniques to all the features of the data set
### STEP 4
Save the data to the file
## PROGRAM
```
Developed by: Sabitha P
Register Number: 212222040137
```
### For Encoding.csv file
```python
import pandas as pd

df=pd.read_csv("/content/Encoding Data.csv")
df

#ORDINAL ENCODER
from sklearn.preprocessing import LabelEncoder,OrdinalEncoder
pm=['Hot','Warm','Cold']
e1=OrdinalEncoder(categories=[pm])
e1.fit_transform(df[["ord_2"]])

df["bo2"]=e1.fit_transform(df[["ord_2"]])
df

#LABEL ENCODER
le=LabelEncoder()
dfc=df.copy()
dfc['ord_2']=le.fit_transform(dfc['ord_2'])
dfc

#ONE HOT ENCODER
from sklearn.preprocessing import OneHotEncoder
ohe=OneHotEncoder(sparse=False)
df2=df.copy()
enc=pd.DataFrame(ohe.fit_transform(df2[['nom_0']]))

df2=pd.concat([df2,enc],axis=1)
df2

pd.get_dummies(df2,columns=['nom_0'])

#BINARY ENCODER
pip install --upgrade category_encoders
from category_encoders import BinaryEncoder
df=pd.read_csv("/content/data.csv")
df

dfb=df.copy()
be=BinaryEncoder()
nd=be.fit_transform(df['Ord_2'])
dfb=pd.concat([df,nd],axis=1)
dfb

#TARGET ENCODER
from category_encoders import TargetEncoder
te=TargetEncoder()
cc=df.copy()
new=te.fit_transform(X=cc['City'],y=cc["Target"])
cc=pd.concat([cc,new],axis=1)
cc

```

# OUTPUT:
![image](https://github.com/sabithapaulraj/ODD2023-Datascience-Ex-05/assets/118343379/f9740b1b-2994-4095-8ae3-8cca28dee0ca)
![image](https://github.com/sabithapaulraj/ODD2023-Datascience-Ex-05/assets/118343379/b4293749-cf80-4f28-867d-53183e64d15e)
![image](https://github.com/sabithapaulraj/ODD2023-Datascience-Ex-05/assets/118343379/96548e7f-b187-41a8-aa03-67924c7341e4)
![image](https://github.com/sabithapaulraj/ODD2023-Datascience-Ex-05/assets/118343379/e34e0da2-ff52-4c0e-b3f9-df8fdcbb79af)

![image](https://github.com/sabithapaulraj/ODD2023-Datascience-Ex-05/assets/118343379/ad488311-9d49-4b69-9022-ec8230ed250a)
![image](https://github.com/sabithapaulraj/ODD2023-Datascience-Ex-05/assets/118343379/2d44d0dc-f90c-47f5-81ee-4d7169dd3060)
![image](https://github.com/sabithapaulraj/ODD2023-Datascience-Ex-05/assets/118343379/395174f6-86d2-44d6-81d9-c40e436b540c)
![image](https://github.com/sabithapaulraj/ODD2023-Datascience-Ex-05/assets/118343379/52423c54-ae53-4abb-8d92-a304ffb625d2)
![image](https://github.com/sabithapaulraj/ODD2023-Datascience-Ex-05/assets/118343379/d7e0a5b3-a2d4-49d6-baca-8efe22b5746e)
![image](https://github.com/sabithapaulraj/ODD2023-Datascience-Ex-05/assets/118343379/47d7250b-f072-42ff-992a-edac63eb9201)
![image](https://github.com/sabithapaulraj/ODD2023-Datascience-Ex-05/assets/118343379/245cb80c-e110-4746-aa11-04790f7837a9)

# RESULT:
Thus,the Feature Generation process is performed on the given dataset.

