
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

I used the given **Forecasts for Product Demand** dataset (https://www.kaggle.com/felixzhao/productdemandforecasting) for this Demand Forecasting modeling assignment. (Data csv file is in /data/historical_product_demand.csv).

### Process:

<ul>
<li>First, I loaded the given csv file into the Pandas Dataframe.</li>
<li>Then, I did feature engineering and also three time based analysis to get some insights about the given dataset. Please refer to notebook for more details.These three analysis are also given below and are Weekly based, Monthly based and Years Weeks based trends.</li>
<li>Finally, we trained and evaluated (forecasted) using the statistics-based ARIMA (Auto Regressive Integrated Moving Average) model to forecast the product demand.</li>
</ul>

### Discussion and Results:
The given dataset, once loaded into the dataframe was as follows:

	Product_Code	Warehouse	Product_Category	Date	Order_Demand
	
0	Product_0993	Whse_J	Category_028	2012-07-27	100

1	Product_0979	Whse_J	Category_028	2012-01-19	500

2	Product_0979	Whse_J	Category_028	2012-02-03	500

3	Product_0979	Whse_J	Category_028	2012-02-09	500

4	Product_0979	Whse_J	Category_028	2012-03-02	500

![](figs/fig1u.png)


![](figs/fig2u.png)

![](figs/fig3u.png)

![](figs/fig4u.png)

![](figs/fig5u.png)

![](figs/fig6u.png)



### Conclusion

This assignment was very unique as we had to do time-series forecasting for product demand over the time, and no conventional classification, regression and other approaches can be used directly with effective results. Thus, it was a challenging task. To get insights into the time-series data, we learnt that some time units (**weekly, monthly, yearly**) are really helpful. Consequently, we analyzed the given dataset using these newly created time based units that gave us valauble insights about the given dataset. Then, we modeled our demand forecasting problem with focus on one product (**Product # 1359**), as this method can be replicated for other products as well. The given dataset was divided into **80/20%** training/testing split. Modeling was done using statistics based **ARIMA (Auto Regressive Integrated Moving Average)** model. The results show reasonable performance of our product demand forecasting system.



