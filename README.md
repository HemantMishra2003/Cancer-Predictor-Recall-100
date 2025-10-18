  #   About the Dataset 
  
This Dataset is about prediction of Lung Cancer . We have so many inputs column 
like taking alochol or not ,  addicting  to smoke or not .
having chest pain or not and so on ...and behalf of these inputs
we we have to predict that a person have cancer or not .....

  #   Our Aim
  
Focus had been over the Recall score then Precision score  and then overall accuracy...
 I w preprocessed  this raw dataset and make trained model 
 by using 14 techniques like  Boosting techniques , bagging
knnn , svm and so on .....

#  accuracy of my model ...

Boosting performed very well..
catboost accuracy
overall : 99.16 %
recall :  100   %
precision : 98.31


#  how to do predictions :

step 1 :
 import pickle library at your own  notebook : 

 
 step 2 : 
      load my trained model which is in pickle format then : write this function 
      
      
      with open('catboost_model(1).pkl', 'rb') as f:
      model = pickle.load(f)
  step 3 :
          load ur test data :

           import pandas as pd
           X_test = pd.read_csv('lung_cancer_test.csv')
           
  step 4 : 
           make predictions : 
          
         y_pred = model.predict(X_test)
         print(y_pred)
         

  
      
