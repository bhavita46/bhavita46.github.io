---
name: Homework 6
tools: [Python, HTML, Vega-Lite, Altair]
image: assets/pngs/visualization.png
description: Using Python, Altair and vega-lite to create two visualizations for HW6
custom_js:
  - vega.min
  - vega-lite.min
  - vega-embed.min
  - justcharts
---


# Homework 6 - Licenses Data Visualizations <br />
<br />
## Plot 1: License Type Distribution by Year


<vegachart schema-url="{{ site.baseurl }}/assets/json/interactive_chart.json" style="width: 100%"></vegachart>
<br />
This bar chart visualizes the distribution of licenses issued in a specific year based on the license type. The License Type is shown along the x-axis, while the y-axis represents the count of licenses issued for each type in the selected year.

Design Choices:

- Encoding Types:
  The x-axis encodes the License Type as a nominal (categorical) variable. The y-axis encodes the Count of Licenses Issued as a quantitative variable. The color encoding is used to differentiate between various license types, with each color representing a distinct license type. Tooltips are added to enhance interactivity, displaying the license type and count when hovering over the bars.

- Color Scheme:
  The colors are based on the License Type, providing a clear distinction between the categories. This makes it easy for viewers to identify trends and compare different license types visually.

Data Transformations:
  The data transformations include converting the Original Issue Date column to datetime format, dropping rows with missing dates, and extracting the year into a new Issue Year column. The dataset is then grouped by Issue Year and License Type, with the size of each group calculated to represent the count of licenses issued. These transformations prepare the data for analyzing license trends by year and type, and enable interactive filtering by year for visualization.
  
Overlap with Homework 5:
  For Homework 6, I am working with a completely different dataset compared to Homework 5. As a result, there is no overlap between the datasets or analyses used in Homework 5 and Homework 6.

Interactivity:
  The slider interactivity lets the user choose a specific year, making it easier to explore how license issuance trends vary over time. By adjusting the year, users can immediately see how the license counts change, which makes the visualization more engaging and informative.


## Plot 2: License Status Distribution

<vegachart schema-url="{{ site.baseurl }}/assets/json/bar_chart.json" style="width: 100%"></vegachart>
<br />
This bar chart shows the distribution of licenses by their status. The x-axis represents the various License Status categories, while the y-axis indicates the number of licenses within each status.

Design Choices:

- Encoding Types:
  The x-axis encodes the License Status as a nominal variable. The y-axis encodes the Count (the number of licenses) as a quantitative variable. Colors differentiate between the license statuses, with a legend provided to clearly identify each status.
- Color Scheme:
  The License Status is mapped to distinct colors to make each category stand out. This helps the viewer quickly identify which statuses are most common (such as “NOT RENEWED”) and how the distribution looks across different categories.

Data Transformations:
  The data transformations performed include counting the occurrences of each unique value in the License Status column using value_counts(), which aggregates the data by license status. This is followed by resetting the index with reset_index() to convert the result into a DataFrame with two columns, which are then renamed to License Status and Count for clarity. Finally, the data is sorted in descending order based on the Count column using sort_values(), ensuring that the most frequent license statuses are displayed first, making it easier to visualize and analyze the distribution of licenses.

Overlap with Homework 5:
  For Homework 6, I am working with a completely different dataset compared to Homework 5. As a result, there is no overlap between the datasets or analyses used in Homework 5 and Homework 6.

Interactivity:
  This plot does not feature interactivity.

<br />
Overall Interactivity of both plots:

In the first plot, the slider interactivity is particularly useful as it allows viewers to explore changes over time in license distribution. Without this feature, it would be harder to observe trends across different years, which could lead to an incomplete understanding of the data. The dynamic filtering provided by the slider adds depth to the analysis and makes the visualization more informative and engaging. Adding similar interactivity to the second plot could enhance exploration of license statuses over time or by license type.
<!-- these are written in a combo of html and liquid --> 

<div class="left">
{% include elements/button.html link="https://raw.githubusercontent.com/UIUC-iSchool-DataViz/is445_data/main/licenses_fall2022.csv" text="The Data" %}
</div>

<div class="right">
{% include elements/button.html link="https://github.com/bhavita46/bhavita46.github.io/blob/main/python_notebooks/Workbook.ipynb" text="The Analysis" %}
</div>

