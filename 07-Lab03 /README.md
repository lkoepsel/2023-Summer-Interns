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
