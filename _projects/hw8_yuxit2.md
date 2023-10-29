---
name: hw8_yuxit2
tools: [Python, HTML, vega-lite]
image: assets/pngs/hw8_interactive_legend.png
description: homework 8
custom_js:
  - vega.min
  - vega-lite.min
  - vega-embed.min
  - justcharts
---

### Exporting plots made in Python+Altair+vegalite


### Chart 1:

<vegachart schema-url="{{ site.baseurl }}/assets/json/jsonchart1_hw8.json" style="width: 100%"></vegachart>


### 1. Description of the Visualization
The visualization is an interactive bar chart representing the number of buildings acquired each year.

### 2. Encoding Types
X-Axis (Horizontal Axis): The x-axis represents the "Year Acquired." It's encoded as an ordinal ("Year Acquired:O") because, although years are numerical, they are being treated as discrete categories in this context. The data is binned to ensure that the chart is not overcrowded, given the potentially large range of years. Specifically, a maximum of 100 bins is set (bin=alt.Bin(maxbins=100)) to strike a balance between granularity and readability.

Y-Axis (Vertical Axis): The y-axis represents the "Number of Buildings" acquired. It's a quantitative encoding, denoted by count(), which tallies the number of buildings acquired in each binned year. The title "Number of Buildings" clearly conveys what is being measured.

A uniform green color (color="green") is used for the bars.

### 3. Data Transformations and Analysis
Binning Transformation: The "Year Acquired" data is binned to group the years into manageable intervals. This transformation simplifies the visualization, especially when dealing with many years of data. It allows viewers to discern patterns and trends more efficiently than they would if each year was represented individually.

Count Aggregation: The y-axis employs a count aggregation function (count()), which calculates the number of buildings acquired in each binned year interval. This transformation is essential for converting raw data into a meaningful metric for visualization.

Interactive Brush Selection: An interactive filter, brush, allows users to select a range of years on the chart. This selection dynamically filters the data to show only the buildings acquired within that range.


## Chart 2:

<vegachart schema-url="{{ site.baseurl }}/assets/json/jsonchart2_hw8.json" style="width: 100%"></vegachart>

### 1. Description of the Visualization
This visualization is an interactive line chart representing the number of buildings constructed each year. 

### 2. Encoding Types
X-Axis (Horizontal Axis): The x-axis encodes the "Year Constructed" as a temporal type. This is appropriate for representing dates and allows the chart to handle the temporal data effectively, ensuring accurate spacing and formatting of dates.

Y-Axis (Vertical Axis): The y-axis represents the "Number of Buildings" constructed each year, encoded with a count aggregate ("aggregate": "count"). This quantitative encoding efficiently communicates the volume of construction activities annually.

The line is using  a default color type.

### 3. Data Transformations and Analysis
Filtering Transformation: Before plotting, the dataset undergoes a filtering process, removing any records where 'Year Constructed' is null or zero. This step is crucial for maintaining data integrity, ensuring that only valid and meaningful data points contribute to the visualization.

Interactive Brush Selection: Similar to the first chart, this visualization also includes an interactive brush selection feature. This tool allows users to select a range of years on the chart, focusing on specific time intervals for a more detailed examination.


## Chart 3:

<vegachart schema-url="{{ site.baseurl }}/assets/json/jsonsied_by_side_interactive_hw8.json" style="width: 100%"></vegachart>

### 1. Description of the Visualization
The combined visualization presents two related but distinct aspects of building inventory data side by side.

### 2. Encoding Types
chart1 Encoding: Ordinal encoding with binning for the "Year Acquired" on the x-axis, and Quantitative count encoding for the "Number of Buildings" on the y-axis.

chart2 Encoding: Temporal encoding for the "Year Constructed" on the x-axis.
Quantitative count encoding for the "Number of Buildings" on the y-axis.

### 3. Data Transformations and Analysis
Binning in chart1: Binning of "Year Acquired" data simplifies the visualization and enhances readability.

Filtering in chart2: Removal of records with null or zero values in "Year Constructed" ensures the accuracy and reliability of the trend analysis.

Interactive Brush Selection: Both charts include an interactive brush selection, allowing users to focus on specific time periods. If the same brush selection is shared between them, selecting a range in one chart will dynamically filter the data in the other chart, enhancing the comparative analysis.



<!-- these are written in a combo of html and liquid --> 

<div class="left">
{% include elements/button.html link="https://raw.githubusercontent.com/UIUC-iSchool-DataViz/is445_data/main/building_inventory.csv" text="The Data" %}
</div>

<div class="right">
{% include elements/button.html link="https://github.com/Yuxit2/Yuxit2.github.io/blob/main/python_notebooks/is445_hw8_yuxit2.ipynb" text="The Analysis" %}
</div>

