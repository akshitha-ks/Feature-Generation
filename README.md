AIM:

    To read the given data and perform Feature Generation process and save the data to a file.
    
EXPLANATION:

      Feature Generation (also known as feature construction, feature extraction or feature engineering) is the process of transforming features into new features that better relate to the target.
      
ALGORITHM:

      Step 1: Read the given data.
      
      Step 2: Clean the Data Set using Data Cleaning Process.
      
      Step 3: Apply Feature Generation techniques to all the feature of the data set.
      
      Step 4: Save the data to the file.
      
CODE:

Encoding Data.csv

import pandas as pd

import numpy as np

import seaborn as sbn

df = pd.read_csv("/content/Encoding Data.csv")

df1 = df.copy()

df1.head(5)

from sklearn.preprocessing import LabelEncoder,OrdinalEncoder

climate = ['Cold','Warm','Hot']

enc = OrdinalEncoder(categories = [climate])

enc.fit_transform(df1[["ord_2"]])

df1['Ord_2'] = enc.fit_transform(df1[["ord_2"]])

df1.head(5)

df2 = df1.copy()

le = LabelEncoder()

df2['Nom_0'] = le.fit_transform(df2[["nom_0"]])

df2.head(5)

df3 = df2.copy()

from category_encoders import BinaryEncoder

be = BinaryEncoder()

data = be.fit_transform(df['bin_1'])

df3 = pd.concat([df,data],axis=1)

df3.head(5)

df4 = df3.copy()

from category_encoders import BinaryEncoder

be1 = BinaryEncoder()

newdata = be.fit_transform(df['bin_2'])

df4 = pd.concat([df,newdata],axis=1)

df4.head(5)

import seaborn as sbn

from sklearn.preprocessing import LabelEncoder

le = LabelEncoder()

df['ord_2'] = le.fit_transform(df['ord_2'])

sbn.set(style ="darkgrid")

sbn.countplot(df['ord_2'])


data.csv

import pandas as pd

import numpy as np

import seaborn as sbn

df = pd.read_csv("/content/data.csv")

df.head(5)

df.info()

df.isnull().sum()

from sklearn.preprocessing import LabelEncoder

le = LabelEncoder()

df['Ord_2'] = le.fit_transform(df['Ord_2'])

sbn.set(style ="darkgrid")

sbn.countplot(df['Ord_2'])

from sklearn.preprocessing import OneHotEncoder

enc = OneHotEncoder()

enc = enc.fit_transform(df[['City']]).toarray()

encoded_colm = pd.DataFrame(enc)

df = pd.concat([df, encoded_colm], axis=1)

df = df.drop(['City'], axis=1)

df.head(10)

df = pd.get_dummies(df, prefix=['Ord_2'], columns=['Ord_2'])

df.head(10)

df = pd.get_dummies(df, prefix=['Ord_1'], columns=['Ord_1'])

df.head(10)


titanic_dataset.csv

import pandas as pd

import numpy as np

import seaborn as sbn

df = pd.read_csv("/content/titanic_dataset.csv")

df.head(5)

df.info()

df.isnull().sum()

df['Age']=df['Age'] . fillna(df['Age'].mean())

df['Cabin']=df['Cabin']. fillna(df['Cabin']. mode() [0])

df['Embarked']=df['Embarked'] . fillna(df['Embarked'].mode( )[0])

df.isnull().sum()

from sklearn.preprocessing import LabelEncoder

lc = LabelEncoder()

df['Sex'] = lc.fit_transform(df['Sex'])

sbn.set(style ="darkgrid")

sbn.countplot(df['Sex'])

from sklearn.preprocessing import OneHotEncoder

enc= OneHotEncoder()

enc= enc.fit_transform(df[['Name']]).toarray()

encoded_colm = pd.DataFrame(enc)

df= pd.concat([df, encoded_colm], axis=1)

df= df.drop(['Name'], axis=1)

df.head(10)

df = pd.get_dummies(df, prefix=['Ticket'] ,columns=['Ticket'])

df.head(10)

df = pd.get_dummies(df, prefix=['Embarked'] ,columns=['Embarked'])

df.head(10)


OUTPUT:

Encoding Data.csv

![image](https://user-images.githubusercontent.com/123535064/232002980-20d85600-668c-4120-a687-2a6b8e678ff2.png)

![image](https://user-images.githubusercontent.com/123535064/232003041-163031aa-04b5-400b-b378-d126cadc200c.png)

![image](https://user-images.githubusercontent.com/123535064/232003078-a2d99a7a-446a-4136-9f20-8c502fed8189.png)

![image](https://user-images.githubusercontent.com/123535064/232003112-18f6cbc3-81c2-40b5-8344-1d4fc3e158aa.png)

![image](https://user-images.githubusercontent.com/123535064/232003134-8d4a1145-2325-4465-8401-f559c29ad855.png)

![image](https://user-images.githubusercontent.com/123535064/232003162-bee02023-ecd2-46ec-92b2-2057cb338e46.png)

![image](https://user-images.githubusercontent.com/123535064/232003199-bd79ddb3-f640-4a7e-a590-3f81696011ca.png)


data.csv

![image](https://user-images.githubusercontent.com/123535064/232005090-6c8b6c98-99bc-4934-9619-e9d27399d217.png)

![image](https://user-images.githubusercontent.com/123535064/232005119-cf9ee637-1765-4f22-a536-15227b4f5bcc.png)

![image](https://user-images.githubusercontent.com/123535064/232005150-4c1df1c0-c6cd-4541-84b1-511e0394b23b.png)

![image](https://user-images.githubusercontent.com/123535064/232005185-3283b56f-a28d-4b3f-9bc5-dae5a92c9598.png)

![image](https://user-images.githubusercontent.com/123535064/232005227-b4a5d648-efa9-4d79-a035-8e1f26344f16.png)

![image](https://user-images.githubusercontent.com/123535064/232005267-74a3f8b1-c7b4-4204-8b2b-399ec529fc02.png)


titanic_dataset.csv

![image](https://user-images.githubusercontent.com/123535064/232005403-93d9029f-287b-449f-ae27-cbe36fa5aed3.png)

![image](https://user-images.githubusercontent.com/123535064/232005443-aed492ce-db4f-4e58-99a9-630304d6dcea.png)

![image](https://user-images.githubusercontent.com/123535064/232005483-a9875469-dd96-4ef0-8bb8-fb7930b62d49.png)

![image](https://user-images.githubusercontent.com/123535064/232005528-76329f5f-7de2-4505-a40d-020b019ba6b7.png)

![image](https://user-images.githubusercontent.com/123535064/232005545-fa001987-606f-4882-9ba4-b7ff33f1c8b0.png)

![image](https://user-images.githubusercontent.com/123535064/232005579-608488f9-4198-465c-902d-4ed57b6f5daf.png)

![image](https://user-images.githubusercontent.com/123535064/232005628-094a99ba-029f-4eb8-8498-80af3d5f62df.png)



RESULT:

      Thus, the program to perform Feature Generation process on the given data set is successfully executed.
