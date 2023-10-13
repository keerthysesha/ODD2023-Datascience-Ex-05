# Feature_Encoding_Scaling
# Ex:05 Feature Generation
# AIM
To read the given data and perform Feature Generation process and save the data to a file.

# Explanation
Feature Generation (also known as feature construction, feature extraction or feature engineering) is the process of transforming features into new features that better relate to the target.

# ALGORITHM
STEP 1
Read the given Data

STEP 2
Clean the Data Set using Data Cleaning Process

STEP 3
Apply Feature Generation techniques to all the feature of the data set

STEP 4
Save the data to the file

# PROGRAM

# For Encoding.csv file
```
import pandas as pd
df=pd.read_csv('Encoding Data.csv')
df.head()
df['ord_2'].unique()
from sklearn.preprocessing import LabelEncoder,OrdinalEncoder
climate = ['Cold','Warm','Hot']
en= OrdinalEncoder(categories = [climate])
df['ord_2']=en.fit_transform(df[["ord_2"]])
df
le = LabelEncoder()
df['Nom_0'] = le.fit_transform(df[["nom_0"]])
df
!pip install --upgrade category_encoders
from category_encoders import BinaryEncoder
be = BinaryEncoder()
data = be.fit_transform(df['bin_1'])
df  = pd.concat([df,data],axis=1)
df
be = BinaryEncoder()
data = be.fit_transform(df['bin_2'])
df  = pd.concat([df,data],axis=1)
df
```

# Data.csv
```
import pandas as pd
df1 = pd.read_csv("data.csv")
df1.head()
df1['Ord_1'].unique()
from sklearn.preprocessing import LabelEncoder,OrdinalEncoder
climate = ['Cold','Warm','Hot','Very Hot']
en= OrdinalEncoder(categories = [climate])
df1['Ord_1']=en.fit_transform(df1[["Ord_1"]])
df1
df1['Ord_2'].unique()
cl = ['High School','Diploma','Bachelors','Masters','PhD']
en= OrdinalEncoder(categories = [cl])
df1['Ord_2']=en.fit_transform(df1[["Ord_2"]])
df1
le = LabelEncoder()
df1['City'] = le.fit_transform(df1[["City"]])
df1
from category_encoders import BinaryEncoder
be = BinaryEncoder()
dat = be.fit_transform(df1['bin_1'])
df1  = pd.concat([df1,dat],axis=1)
df1
from category_encoders import BinaryEncoder
be = BinaryEncoder()
data1 = be.fit_transform(df1['bin_2'])
df1  = pd.concat([df1,data1],axis=1)
df1
```
# BMI.csv file
```
import pandas as pd
df2 = pd.read_csv("/content/bmi.csv")
df2.head()
be = BinaryEncoder()
data2 = be.fit_transform(df2['Gender'])
df2  = pd.concat([df2,data2],axis=1)
df2
df2 = pd.get_dummies(df2, prefix=['Index'] ,columns=['Index'])
df2
```
## OUTPUT
# For encoding.csv file
# Initial data:
![image](https://github.com/keerthysesha/ODD2023-Datascience-Ex-05/assets/125575936/e95e5f80-3964-4b4d-80a3-406ae659fc86)


# Unique value:
![image](https://github.com/keerthysesha/ODD2023-Datascience-Ex-05/assets/125575936/09c3abc0-5b5f-4969-b800-1ecb13d2f499)


# Ordinal Encoder:
![image](https://github.com/keerthysesha/ODD2023-Datascience-Ex-05/assets/125575936/a4034832-f33f-4370-9093-1f69ac0fb5f5)


# Label Encoder:
![image](https://github.com/keerthysesha/ODD2023-Datascience-Ex-05/assets/125575936/90f06e37-6d70-42ff-899b-6e05369af6aa)


# Binary Encoder:
![image](https://github.com/keerthysesha/ODD2023-Datascience-Ex-05/assets/125575936/6f6f296a-29ac-4cd2-ac00-a30c9ed51a3d)


![image](https://github.com/keerthysesha/ODD2023-Datascience-Ex-05/assets/125575936/b0fbfe02-20ce-4cae-8e13-ff0d6c13df3c)


# For Data.csv file
# Initial data:
![image](https://github.com/keerthysesha/ODD2023-Datascience-Ex-05/assets/125575936/c282b755-9d58-401e-9575-209402d4b122)


# Unique data:
![image](https://github.com/keerthysesha/ODD2023-Datascience-Ex-05/assets/125575936/dd11014d-91ea-4fbf-9e06-3e5bce9ba1f5)


# Ordinal Encoder:
![image](https://github.com/keerthysesha/ODD2023-Datascience-Ex-05/assets/125575936/56beedc7-268e-41d3-b5a7-0fba5875c3cd)


![image](https://github.com/keerthysesha/ODD2023-Datascience-Ex-05/assets/125575936/c07caa60-3e96-41ef-91da-e2d2a0087188)


# Label Encoder:
![image](https://github.com/keerthysesha/ODD2023-Datascience-Ex-05/assets/125575936/ade3d055-08e7-4580-a109-30e476b96389)


# Binary Encoder:
![image](https://github.com/keerthysesha/ODD2023-Datascience-Ex-05/assets/125575936/363ce244-822a-4e78-b01c-8247d132444e)


![image](https://github.com/keerthysesha/ODD2023-Datascience-Ex-05/assets/125575936/da504fbd-c4b0-43c2-af16-b6d41c7fbc28)


# For bmi.csv file
# Initial data:
![image](https://github.com/keerthysesha/ODD2023-Datascience-Ex-05/assets/125575936/919cf216-7b77-432f-89fa-818ba644f672)


# Binary Encoders:
![image](https://github.com/keerthysesha/ODD2023-Datascience-Ex-05/assets/125575936/b0fe0bed-c4a0-434c-8f13-88178e570dd5)


# Dummies:
![image](https://github.com/keerthysesha/ODD2023-Datascience-Ex-05/assets/125575936/53e1f419-bbc4-465a-b823-a7c3d10007fe)


## RESULT:
The Feature Generation process was performed and saved the data to a file.
