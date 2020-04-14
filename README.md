# Simple outlier detection

## TASK: visualize outliers in a aggregated time series

The <a target="_blank" href="https://www.kaggle.com/c/avazu-ctr-prediction">data</a> is made available by Kaggle and is used to
calculate the click-through rate (CTR), a very important metric for evaluating ad performance. 

I have imported a sample of the underlying raw data into this notebook and performed some initial EDA, then I calculated the CTR on aggregated hour data and identified some periodicity of the values within the 10 available days.

When aggregating over daily hours, we find out that midnight concentrates the lowest absolute click values, but also the highest CTR, so it seems people are more prone to click at this time.

In the second part I built a simple outlier detection algorithm based on the idea behind the Bollinger Band statistical chart - an approach used frequently to analyse fluctuations in the financial/stock market. For this purpose I have used a Simple Moving Average with a 3 hours window, which did a pretty good job by capturing the pattern of the data - returning no outliers. 

By using a window of 5 hours the results were deteriorated by the daily periodical variance of data, leading to the appearance of some outliers - highlited in the plot. This simple analysis shows how important it is to select an appropriate window size for calculating the simple moving average and how it is sensitive to periodical/cyclical changes in data.

Further steps involve trying other moving averages (CMA, EMA...) and defining hour-based moving average.
