# Google Trends Analysis Project

## Introduction
A large number of searches are made each second, and with the digital age approaching, understanding and analyzing ongoing trends is essential. This project uses Google Trends data to explore search interest trends over time. The goal is to identify patterns in the popularity of specific search terms, seasonal patterns, and derive actionable insights.

## Problem Statement
This project aims to:
- Analyze the trends and popularity of certain terms over time.
- Identify seasonal patterns in search interest.
- Derive actionable insights based on search data.

## Keywords Analyzed
- `data science`
- `machine learning`
- `artificial intelligence`
- `finance`
- `business`

## Methodology
1. **Data Collection:**
   - Google Trends data was retrieved using the `pytrends` library.
   - Timeframe analyzed: `2020-01-01` to `2024-01-01`.
2. **Data Analysis:**
   - Plotted interest over time for keywords.
   - Normalized and compared trends.
   - Used rolling averages to smooth trends.
   - Correlation analysis was performed between keywords.
   - Seasonal and long-term trends were analyzed using STL decomposition.
3. **Visualization:**
   - Matplotlib and Plotly were used for creating interactive and static visualizations.

## Tools and Libraries
- Python
- `pytrends`
- `pandas`
- `matplotlib`
- `statsmodels`
- `plotly`

## Analysis
### Trends
- Increasing interest trends observed for `data science` and `machine learning`.
- `finance` and `business` had consistently higher search interest compared to technical terms.

### Seasonality
- Detected seasonal spikes in search interest for `artificial intelligence`, likely tied to industry events or major announcements.

### Correlation
- A strong positive correlation was identified between `data science` and `machine learning`.

### Visualizations
- **Interest Over Time:** Time series plots for keywords.
- **Normalized Trends:** Comparison of normalized search interest.
- **Rolling Averages:** Smoothed trends using a 12-month rolling average.
- **STL Decomposition:** Seasonal and trend decomposition for `data science`.

## Code Highlights
### Fetching Data
```python
from pytrends.request import TrendReq
pytrends = TrendReq(hl='en-US', tz=360)
keywords = ['data science', 'machine learning', 'artificial intelligence', 'finance', 'business']
timeframe = '2020-01-01 2024-01-01'
pytrends.build_payload(keywords, timeframe=timeframe)
data = pytrends.interest_over_time()
```

### Visualizing Trends
```python
import matplotlib.pyplot as plt
# Plotting search interest over time
data.plot(figsize=(12, 6))
plt.title('Interest Over Time')
plt.xlabel('Date')
plt.ylabel('Interest')
plt.legend(keywords)
plt.grid(True)
plt.show()
```

### STL Decomposition
```python
from statsmodels.tsa.seasonal import STL
stl = STL(data['data science'], period=12)
result = stl.fit()
result.plot()
plt.show()
```

## Insights
- `Data Science`: Steady growth indicates rising demand for related skills.
- `Artificial Intelligence`: Seasonal spikes suggest relevance to industry events or major releases.

## Conclusion
This analysis provides valuable insights into search interest trends, which can inform marketing strategies, educational content development, and industry forecasting. Understanding these trends can help stakeholders stay ahead in a rapidly evolving technological landscape.

## Future Work
- Include more keywords for a broader analysis.
- Extend the timeframe for long-term trend analysis.
- Incorporate external factors (e.g., industry reports) to enhance insights.

## How to Use
1. Clone the repository.
2. Install dependencies: `pip install -r requirements.txt`.
3. Run the provided Jupyter Notebook or Python scripts.

## License
This project is licensed under the MIT License.

---
Feel free to contribute by suggesting improvements or extending the analysis!

