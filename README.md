
World Wide Products Inc. (Assignment # 05- EECS 731)
==============================


### Quick Note:
If you are interested in only looking at notebook, please access the notebook in **/notebooks/time_series_forecasting.ipynb**.

/notebooks: Contains the notebook of this assignment.

/data: Contains the data csv file (historical_product_demand.csv)

### Objective:

<ul>
<li>Load the given Time series dataset for different products demand information in a Pandas Dataframe</li>
<li>Do feature engineering to analyze the dataset and add value to it in terms of valuable insights</li>
<li>Design the forecasting model to determine the demand for a particular product using the other columns as features</li>
</ul>

### Dataset:

I used the **Machine Temperature System Failure** dataset (https://github.com/numenta/NAB/tree/master/data) for this Anomaly Detection modeling assignment. (Data csv file is in /data/machine_temperature_system_failure.csv).

### Process:

<ul>
<li>First I did feature engineering. Please refer to notebook for more details.</li>
<li>Then, I did change in value over time graphical analysis and EMWA graphical analysis on the given dataset.</li>
<li>Finally, we trained and evaluated two anomaly detection based models separately on the given dataset to detect anomalies.</li>
</ul>

### Discussion and Results:
According to the given dataset we are using, there are **three anomalies** in it. We have to detect these anomalies using some Machine Learning Algorithm suitable for this problem. First we analyze the dataset and anomalies by making a time plot as follows:

![Given Dataset Over Time Graph](figs/fig1u.png)


As shown above, we can see three anomalies. The left-most anomaly is easy to detect, but next two anomalies are much closer to the normal data points. So, this makes it a challenging task for us. Next, to analyze the change in value over time for different data points, we plot the value change per datapoint over time as follows:

![Change in Value Over Time Graph](figs/fig2au.png)

As shown in the above graph, we can now clearly see that three anomalies have the highest peaks or changes as compared to other data points. It makes it more clearer to us. Now we can focus on these anomalous data points and model algortihms for their detection. We use this information in our modeling process as detailed in the notebook. Before starting the modeling process, we also analyze the Exponentially Weighted Moving Averages (EMWA) that are helpful in smoothing the graph as follows. But we skip them being not much useful.


![EMWA Over Time Graph](figs/fig2u.png)


For modeling the Anomaly Detection problem, we trained and evaluated following two algorithms:


<ul>
<li>One Class SVM</li>
<li>Isolation Forest Model</li>
</ul>

Their training process has been given in the notebook. Once they have been modeled separately, their evaluation results for anomaly detection are given in the following two graphs:

![Once Class SVM based Anomaly Detection Graph](figs/fig3u.png)




![Isolation Forest based Anomaly Detection Graph](figs/fig4u.png)


As it can be seen from the above two graphs, One class SVM is quite efficient but not very accurate relatively, as it also labels other normal data points incorrectly as anomalous. On the other hand, Isolation Forest model is comparatively more accurate and effective, but lesser efficient with more computational time.



### Conclusion

This assignment was very unique as we had to do time-series forecasting for product demand over the time, and no conventional classification, regression and other approaches can be used directly with effective results. Thus, it was a challenging task. To get insights into the time-series data, we learnt that some time units (**weekly, monthly, yearly**) are really helpful. Consequently, we analyzed the given dataset using these newly created time based units that gave us valauble insights about the given dataset. Then, we modeled our demand forecasting problem with focus on one product (**Product # 1359**), as this method can be replicated for other products as well. The given dataset was divided into **80/20%** training/testing split. Modeling was done using statistics based **ARIMA (Auto Regressive Integrated Moving Average)** model. The results show reasonable performance of our product demand forecasting system.



