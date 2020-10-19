# EECS_731_MS_Project_6
   The real world does not slow down for bad data
1.  Set up a data science project structure in a new git repository in your GitHub account
2.  Download the benchmark data set from
https://www.kaggle.com/boltzmannbrain/nab  or
https://github.com/numenta/NAB/tree/master/data
3.  Load the  one  of the data set into panda data frames
4.  Formulate one or two ideas on how feature engineering would help the data set to establish additional value using exploratory data analysis
5.  Build one or more anomaly detection models to determine the  anomalies  using the other columns as features
6.  Document your process and results
7.  Commit your notebook, source code, visualizations and other supporting files to the git repository in GitHub

This project is a playground for anomalie detection. I selected the dataset from kaggle and office temperature data. As expected, the temperature in the office hovered around 70 degrees. After dome basic data manipulation and visuialization I could graphically see several anomalies both high and low temperatures as well as seasonal trends. For the seasonal trends the increase in temperature outside led to a cooler inside temperature. I decided to neglect seasonal effects; however I split the data into days of the week and weekends as well as day and night for those two contitions. 
Once those features were created they were grouped to see the distribution of temperatures amond the different days. We say that the temperature was closest to the average on a work day during the day so no suprises. Also we could see the weekendsdays were generally the coldest. 
I then took those features and ran them through a one class SVN amd an isolation trees anomaly detection model. The isolation tree model is based on finding the shortest path between random points and the anomalies will have a much different distance. This worked well for detecting the most differen anomalies. I saw that there were some points near the mean that this model was flagging as anomolies, so I engineered another feature where I normalized the temperature by subtracting the mean from the value and squared the result. This created a difference model that showed a magnitude of an anomalie. I think that this worked better but there was a loss of the value of the anomalie. 
Overall both methods were capable of detecting the largest changes in the temperature and classify them as anomalies. 
