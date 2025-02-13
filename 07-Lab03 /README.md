# README Notes for 07 Lab03

Instructions
This lab will be completed in a JuypterLab notebook with all calculations being performed using Python and text will be in Markdown. **Once the notebook is complete, please export an HTML version of the notebook and add that to your repository as well.** When you push your repository to GitHub, be sure that both the .ipynb and .html versions are included.


## Links for Videos
* [Accelerated Motion - Tracker](https://www.youtube.com/watch?v=PSRaSouIm6M)
* [Accelerated Motion Data with Graphs](https://www.youtube.com/watch?v=tKaLO0VD7wA)


## Hints on Reading Data
The four *csv* files contain the data for the 4 runs mentioned in the second video. **You do not need to use the Google sheets referenced file.** Be sure to download the files to your folder and load them into your notebook for analysis.

If you have issues with the header file showing up as data, use the following command:
```python
import pandas as pd
import plotly.express as px
df = pd.read_csv("Accelerated Motion DATA - run 02.csv", header=1)
display(df)
```

## Bad Data
For your analysis, it is important to remove or not consider the bad data as part of your dataset. As shown in the video, bad data would be where the puck was being hand pushed up the incline and where it had rebounded off the bumper at the bottom. Do not include these data points in your analysis.

## Referencing the Data
Be sure to use the complete header name when referring to a specific column of data. For example, the name of the first column is not *"t"* it is *"t (s)"* and so on.

## Tables in Lab
Any table in the lab, need to be created using Python, not Markdown. The calculations must be dynamic so that if the data changes, the table values change. Make sure there are appropriate headings per the lab guidance as well (using Python).

## Determining Trendline for Plots
https://stackoverflow.com/questions/63341840/plotly-how-to-find-coefficient-of-trendline-in-plotly-express
1. Install `statsmodels` using the following command: `conda install -c conda-forge statsmodels`
2. To get a trendline in the scatter plot, add `import statsmodels` at the top of your notebook **AND** add the following parameter: `trendline="ols"` to your scatter plot command.
3. Remember you will need to use only your good values, don't include the bad data as mentioned above. The process to do separate the data is this:
```python
pd.set_option('display.max_rows', None)
display(df)
#. Determine where the data changes
display(df[29:240])
# then plot using
fig = px.scatter(df[29:240], x="t (s)", y="v_{x} (m/s)", trendline="ols")
fig.show()
```
4. More than likely the trendline will sit "on-top" of your scatter diagram. Which means we will want to look at the trendline statistics. The equation for a line on a graph is *y = mx +b* where m is the slope of the line and b is the y-intercept. In our case, we can print these two coefficients using the following:
```python
results = px.get_trendline_results(fig)
results = results.iloc[0]["px_fit_results"].params
print(results)
```
When you print the results, you will have two numbers, the first number if *b* or the *y-intercept* and the second is *m*, the *slope of the line*. The slope will also be equal to *a = g(h/100)*, for which you will want to solve for *g* to determine your experimental gravity.
