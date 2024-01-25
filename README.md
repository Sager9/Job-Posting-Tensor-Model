# Job-Posting-Tensor-Model
Summary:
The goal of the project was to design a model to analyze job postings and decide if they were fake or not based on a training data set provided by Kaggle at the address below.
https://www.kaggle.com/datasets/shivamb/real-or-fake-fake-jobposting-prediction/data
In Tensorflow_Model/Tensorflow_Model.ipynb the data is processed so it can be fed into a Tensorflow model. The trained model is then tested against a partitioned off part of the data set to determine its effectiveness. Once the model was fine tuned it was put to use in website/app.py. The app takes Indeed job posting urls, scrapes the job posting for information and runs the data given against the model to determine whether or not the posting is legitimate or not which is then displayed in website/predict.py.

Issues Faced: The data set is heavily skewed with 95% of the data being legitimate job postings so when the model was initially run it came back with an accuracy of 95% but just predicted every posting was legitimate. To address this I had to reduce the amount of legitimate entries in the data set and change how heavily the model weighed the true and false sets. Changing the prediction cut off point in website/predict.py was also required so the model would only predict fraud if it was over 90% sure. Otherwise it would predict legitimate.  
