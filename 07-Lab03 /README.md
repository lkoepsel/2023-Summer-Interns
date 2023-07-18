# README Notes for 07 Lab03

Instructions
This lab will be completed in a JuypterLab notebook with all calculations being performed using Python and text will be in Markdown. **Once the notebook is complete, please export an HTML version of the notebook and add that to your repository as well.** When you push your repository to GitHub, be sure that both the .ipynb and .html versions are included.


## Links for Videos
* [Accelerated Motion - Tracker](https://www.youtube.com/watch?v=PSRaSouIm6M)
* [Accelerated Motion Data with Graphs](https://www.youtube.com/watch?v=tKaLO0VD7wA)


## Hints on Reading Data
The four *csv* files contain the data for the 4 runs mentioned in the second video. **You do not need to use the Google sheets referenced file.**
If you have issues with the header file showing up as data, use the following command:
```python
import pandas as pd
import plotly.express as px
df = pd.read_csv("Accelerated Motion DATA - run 02.csv", header=1)
display(df)
```
