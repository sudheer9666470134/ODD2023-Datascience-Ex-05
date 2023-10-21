# Ex:05 Feature Generation
### Aim:
To read the given data and perform Feature Generation process and save the data to a file.
### Explanation:
Feature Generation (also known as feature construction, feature extraction or feature engineering) is the process of transforming features into new features that better relate to the target.
### Algorithm:
Step1: Read the given Data.

Step2: Clean the Data Set using Data Cleaning Process.

Step3: Apply Feature Generation techniques to all the feature of the data set.

Step4: Save the data to the file.
### Program:

- Encoding.csv:
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
from category_encoders import BinaryEncoder
be = BinaryEncoder()
data = be.fit_transform(df['bin_1'])
df = pd.concat([df,data],axis=1)
df
be = BinaryEncoder()
data = be.fit_transform(df['bin_2'])
df = pd.concat([df,data],axis=1)
df
```
 ### Output:
 
initial data:

![274622148-b46c2673-6e5f-4ecb-92b9-7a380b37908a](https://github.com/22002102/ODD2023-Datascience-Ex-05/assets/119091638/d30275a5-b44f-43ab-971b-414b755da48d)

 Unique data:
 
![274622594-27ab6d79-680e-466f-8d6b-a03f4508397c](https://github.com/22002102/ODD2023-Datascience-Ex-05/assets/119091638/9074c13b-e06f-45c2-92ef-c9ddbbb08f7d)

 Original Encoder:
 
![274624836-37731dd9-1302-4dde-84ac-434dd52a4945](https://github.com/22002102/ODD2023-Datascience-Ex-05/assets/119091638/97cbdb20-074c-4708-ac5a-3765908e3e98)

Label Encoder:

![274624847-e9fd27ca-93ba-47a7-9b69-8ac0c1bc06fe](https://github.com/22002102/ODD2023-Datascience-Ex-05/assets/119091638/7cace677-0ac5-4d2b-9738-1d37f74ab089)

Binary Encoder:

![274624863-adffa9d7-4a6a-4de2-827e-2f41bd7560ee](https://github.com/22002102/ODD2023-Datascience-Ex-05/assets/119091638/895a43ad-3846-4c1d-858a-6e39b4165a06)

![274624897-3a6f8f34-7028-4d2f-9d84-cce7b2853d2a](https://github.com/22002102/ODD2023-Datascience-Ex-05/assets/119091638/5ad2e7f3-a7c6-4574-867d-053f73f47f74)


- Data.csv:
```
import pandas as pd
df1 = pd.read_csv("data.csv")
df.head()
df['Ord_1'].unique()
from sklearn.preprocessing import LabelEncoder,OrdinalEncoder
climate = ['Cold','Warm','Hot','Very Hot']
en= OrdinalEncoder(categories = [climate])
df['Ord_1']=en.fit_transform(df[["Ord_1"]])
df.head()
df['Ord_2'].unique()
cl = ['High School','Diploma','Bachelors','Masters','PhD']
en= OrdinalEncoder(categories = [cl])
df['Ord_2']=en.fit_transform(df[["Ord_2"]])
df.head()
le = LabelEncoder()
df['City'] = le.fit_transform(df[["City"]])
df.head()
from category_encoders import BinaryEncoder
be= BinaryEncoder()
data= be.fit_transform(df['bin_1'])
df= pd.concat([df,data],axis=1)
df.head()
from category_encoders import BinaryEncoder
be = BinaryEncoder()
data1 = be.fit_transform(df['bin_2'])
df= pd.concat([df1,data1],axis=1)
df  
```

Output:

Initial data:

![274630974-9015df9d-e8a6-4267-acc6-80179e575384](https://github.com/22002102/ODD2023-Datascience-Ex-05/assets/119091638/1042ec41-013c-4c79-898e-2e681785a51d)

Unique data:

![274631114-7355573d-0c9a-4699-aa3b-21da0ea34136](https://github.com/22002102/ODD2023-Datascience-Ex-05/assets/119091638/95c0f8c1-c7f9-4a9e-914d-14df49776d96)

Original Encoder:

![274631154-55a3e602-a104-439e-8f7a-d5131b41af49](https://github.com/22002102/ODD2023-Datascience-Ex-05/assets/119091638/49ca119a-e07f-446a-9ce5-de33a7553050)


![274631420-8d34dec8-2bf1-4be4-a017-53a3f66567d9](https://github.com/22002102/ODD2023-Datascience-Ex-05/assets/119091638/b1aeec37-027f-4cb9-b288-4c91122e81a5)


Label Encoder:

![274631475-aef111d5-ed57-48d0-bf06-ecb4bba9dc25](https://github.com/22002102/ODD2023-Datascience-Ex-05/assets/119091638/fe64fa73-9c1f-43f6-b73a-200455eaa4ff)

Binary Encoder:

![274631520-67b4b397-d891-48b3-9b02-7bd67d6e192f](https://github.com/22002102/ODD2023-Datascience-Ex-05/assets/119091638/d6652ea1-e474-4090-9d1c-120b141be1f5)


![274631583-9211db6c-364d-4310-8c47-38a151d95d7f](https://github.com/22002102/ODD2023-Datascience-Ex-05/assets/119091638/ff6a9f0d-c98a-4549-ba5c-221a3ebd2a2d)


### BMI.csv:
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
### Output:

 Initial data:
 
![274799301-532fcf97-f3bc-424e-9bac-e7157fc98ba8](https://github.com/22002102/ODD2023-Datascience-Ex-05/assets/119091638/bbe3c6c8-91fe-4c75-adc1-f79ceb9f044a)

Binary Encoder:

![274799308-d09bc5ef-7b73-4ed9-b21a-57535b9ceaf2](https://github.com/22002102/ODD2023-Datascience-Ex-05/assets/119091638/ed4bbc52-e877-4eab-b781-cc07e088a278)

Dummies:

![274799314-071fdcea-6db7-48d7-bf64-3dcca16864f5](https://github.com/22002102/ODD2023-Datascience-Ex-05/assets/119091638/8df43b18-6c6b-4b96-bbbb-51015dd14a91)

### Result:
The Feature Generation process was performed and saved the data to a file.

