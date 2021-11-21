# Linear_SVM
# Linear SVM  in this model we will build a linear SVM to detect the Iris Virginica flowers  
#importing the required libraries  
import numpy as np
import pandas as pd 
from sklearn import datasets
from sklearn.pipeline import Pipeline 
from sklearn.preprocessing import StandardScaler 
from sklearn.svm import LinearSVC
#LinearSVC is a Suport vector clasifier 
All the required Libraries are imported now we will import the data set  
#loading the data from datasets
iris = datasets.load_iris()
Now we got the data lets Lets make the feature variable and Target variable
X = iris['data'][:,(2,3)] # we are reading petal length and width
y = (iris['target']==2).astype(np.float64) # those are only Virginica 
pd.DataFrame(X).head() 
pd.DataFrame(y).head()  
we have set our feature variable and our target variable and we have seen how they look like  Lets build a pipeline for scaling and model Instatiation 
svm_clf = Pipeline([     ('scaler' , StandardScaler()),     ('linear_svc', LinearSVC(C=1, loss = 'hinge')), ]) 
Lets fit our model  
svm_clf.fit(X, y)  
we have trained our model lets see its prediction 
#we are giving the values of the first row in the X svm_clf.predict([[1.4, 0.2]])  
we got the first row of y   
# This is how an Linear SVM works...  Thank you
