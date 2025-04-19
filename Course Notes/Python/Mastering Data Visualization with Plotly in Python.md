---
cssclasses: academia
title: Mastering Data Visualization with Plotly in Python
source: 
  https://blog.enterprisedna.co/mastering-data-visualization-with-plotly-in-python/
description:
tags:
  - data_visualization
  - line_plot
  - plotly
  - python
  - scatter_plot
aliases:
  - Data Viz with Python
  - Plotly Tutorial
key_concepts:
  - Advanced plot techniques
  - Create scatter plots
  - Customize plot appearance
  - Interactive dashboards
  - Plotly library
---

# Mastering Data Visualization with Plotly in Python

- Introduction to Plotly and Basic Plotting
	- Overview
	- Setup
	- Basic Plotting
		- Importing the Library
		- Creating a Simple Scatter Plot
		- Creating a Line Plot
		- Creating a Bar Plot
	- Conclusion
- Customizing Plots for Enhanced Visual Appeal
	- Example: Customizing a Line Plot
		- Step 1: Import Libraries
		- Step 2: Create Basic Data
		- Step 3: Create Basic Line Plot
		- Step 4: Customize Plot – Add Titles and Labels
		- Step 5: Customize Colors and Style
		- Step 6: Add Gridlines and Background Color
		- Step 7: Add Annotations and Shapes
		- Step 8: Final Layout Adjustments
		- Step 9: Display the Customized Plot
	- Advanced Plot Types and Techniques
		- 3 D Scatter Plots
		- Subplots
		- Animated Plots
	- Integrating Plotly with Pandas for Data Analysis
		- Step 1: Import Libraries
		- Step 2: Load Your Dataset
		- Step 3: Data Preparation and Analysis
		- Step 4: Create a Plotly Visualization
		- Step 5: Additional Plotly Features
		- Step 6: Save the Plot
- Interactive Dashboards with Plotly Dash
	- Prerequisites
	- Example: Building a Sales Data Dashboard
		- Step 1: Import Required Libraries
		- Step 2: Load and Prepare Your Data
		- Step 3: Initialize the Dash App
		- Step 4: Define the Layout
		- Step 5: Create Callback Function
		- Step 6: Run the App

Introduction to Plotly and Basic Plotting
-----------------------------------------

Overview
--------

This first part of our course is designed to introduce you to Plotly,  a powerful and flexible library for creating interactive plots and dashboards in Python. In this section,  we’ll cover the basics of setting up Plotly and how to create simple plots.

Setup
-----

To get started with Plotly,  you will need to install the library. You can install it via pip:

![Sales Now On Advertisement](https://enterprisedna.co/pricing)

```python
pip install plotly

```

Basic Plotting
--------------

### Importing the Library

First,  import the necessary modules from Plotly:

```python
import plotly.graph_objects as go

```

### Creating a Simple Scatter Plot

A scatter plot is a great way to visualize relationships between variables. Here’s an example of how to create a simple scatter plot using Plotly:

```python
# Import required libraries
import plotly.graph_objects as go

# Sample data
x_data = [1,       2,       3,       4,       5]
y_data = [10,       15,       13,       17,       20]

# Create a scatter plot
scatter_plot = go.Figure(data=go.Scatter(x=x_data,       y=y_data,       mode='markers'))

# Add title and labels
scatter_plot.update_layout(
    title='Basic Scatter Plot',      
    xaxis_title='X Axis',      
    yaxis_title='Y Axis'
)

# Show plot
scatter_plot.show()

```

### Creating a Line Plot

A line plot is useful for visualizing trends over time or continuous data. Here’s how to create a simple line plot:

```python
# Create a line plot
line_plot = go.Figure(data=go.Scatter(x=x_data,       y=y_data,       mode='lines'))

# Add title and labels
line_plot.update_layout(
    title='Basic Line Plot',      
    xaxis_title='X Axis',      
    yaxis_title='Y Axis'
)

# Show plot
line_plot.show()

```

### Creating a Bar Plot

Bar plots are suitable for comparing quantities. Here’s a basic example:

```python
# Sample data
categories = ['A',       'B',       'C',       'D',       'E']
values = [5,       10,       15,       10,       5]

# Create a bar plot
bar_plot = go.Figure(data=go.Bar(x=categories,       y=values))

# Add title and labels
bar_plot.update_layout(
    title='Basic Bar Plot',      
    xaxis_title='Categories',      
    yaxis_title='Values'
)

# Show plot
bar_plot.show()

```

Conclusion
----------

In this section,  you’ve learned how to install Plotly and create basic scatter,  line,  and bar plots. These fundamental skills will serve as the bedrock for more advanced visualizations we’ll cover in the subsequent parts of this course.

Make sure to practice these examples and experiment with different data to get comfortable with using Plotly for basic plotting tasks.

Customizing Plots for Enhanced Visual Appeal
--------------------------------------------

In this section,  we will take basic plots created using Plotly and customize them to enhance their visual appeal. We will include various elements such as titles,  labels,  color schemes,  and layout adjustments.

![Power BI Tools Advertisement](https://enterprisedna.co/learning-paths)

Example: Customizing a Line Plot
--------------------------------

### Step 1: Import Libraries

```python
import plotly.graph_objects as go
import plotly.express as px

```

### Step 2: Create Basic Data

```python
# Sample data
x_data = [1,       2,       3,       4,       5]
y_data = [10,       14,       12,       16,       14]

```

### Step 3: Create Basic Line Plot

```python
fig = go.Figure()
fig.add_trace(go.Scatter(x=x_data,       y=y_data,       mode='lines+markers',       name='Sample Data'))

```

### Step 4: Customize Plot – Add Titles and Labels

```python
fig.update_layout(
    title='Customized Line Plot',      
    xaxis_title='X Axis',      
    yaxis_title='Y Axis'
)

```

### Step 5: Customize Colors and Style

```python
fig.update_traces(
    line=dict(color='royalblue',       width=2),      
    marker=dict(size=10,       color='red')
)

```

### Step 6: Add Gridlines and Background Color

```python
fig.update_xaxes(
    showgrid=True,       gridwidth=1,       gridcolor='LightPink',      
    zeroline=False
)
fig.update_yaxes(
    showgrid=True,       gridwidth=1,       gridcolor='LightGreen',      
    zeroline=False
)
fig.update_layout(
    plot_bgcolor='rgba(0,      0,      0,      0)',       # transparent
    paper_bgcolor='rgba(255,      255,      255,      1)' # white
)

```

### Step 7: Add Annotations and Shapes

```python
fig.add_annotation(
    x=3,       y=12,      
    text='Annotation Example',      
    showarrow=True,      
    arrowhead=1
)

fig.add_shape(
    type="rect",      
    x0=1,       y0=10,       x1=5,       y1=16,      
    line=dict(color="RoyalBlue")
)

```

### Step 8: Final Layout Adjustments

```python
fig.update_layout(
    font=dict(
        family="Courier New,       monospace",      
        size=18,      
        color="#7f7f7f"
    )
)

```

### Step 9: Display the Customized Plot

```python
fig.show()

```

This practical implementation shows how to create and customize a basic line plot using Plotly. You can extend these principles to other types of plots and further customize the appearance to suit your needs.

Advanced Plot Types and Techniques
----------------------------------

In this part,  we will cover three advanced plotting techniques using the Plotly library in Python: 3 D Scatter Plots,  Subplots,  and Animated Plots.

### 3 D Scatter Plots

A 3 D scatter plot allows for plotting three-dimensional data points.

```python
import plotly.graph_objs as go
from plotly.subplots import make_subplots

# Sample Data
x = [1,       2,       3,       4,       5]
y = [10,       11,       12,       13,       14]
z = [5,       6,       7,       8,       9]

# Create 3D Scatter Plot
fig = go.Figure(data=[go.Scatter3d(x=x,       y=y,       z=z,       mode='markers')])

# Update Layout
fig.update_layout(title='3D Scatter Plot',       scene=dict(
                    xaxis_title='X AXIS',      
                    yaxis_title='Y AXIS',      
                    zaxis_title='Z AXIS'))

fig.show()

```

### Subplots

Subplots allow you to plot multiple plots within the same figure,  which can be useful for comparing different datasets or plot types.

```python
import plotly.graph_objs as go
from plotly.subplots import make_subplots

# Create SubPlots: 2 rows,       2 columns
fig = make_subplots(rows=2,       cols=2)

# Add first subplot
fig.add_trace(
    go.Scatter(x=[1,       2,       3],       y=[10,       11,       12]),      
    row=1,       col=1
)

# Add second subplot
fig.add_trace(
    go.Bar(x=[1,       2,       3],       y=[10,       11,       12]),      
    row=1,       col=2
)

# Add third subplot
fig.add_trace(
    go.Scatter(x=[1,       2,       3],       y=[12,       13,       14]),      
    row=2,       col=1
)

# Add fourth subplot
fig.add_trace(
    go.Bar(x=[1,       2,       3],       y=[12,       13,       14]),      
    row=2,       col=2
)

# Update Layout
fig.update_layout(title='Subplots Example')

fig.show()

```

### Animated Plots

Animated plots can be useful for visualizing changes in data over time.

```python
import plotly.graph_objs as go
import plotly.express as px

# Sample Data
df = px.data.gapminder()

# Create Animated Plot
fig = px.scatter(df,       x="gdpPercap",       y="lifeExp",       animation_frame="year",       animation_group="country",       
                 size="pop",       color="continent",       hover_name="country",       log_x=True,       size_max=55,       
                 range_x=[100,      100000],       range_y=[25,      90])

# Update Layout
fig.update_layout(title='Animated Plot Example')

fig.show()

```

These examples provide hands-on techniques for creating advanced plots using Plotly in Python. Each section focuses on a different type of plot,  showing how to implement them with real data and providing clear,  executable code.

Integrating Plotly with Pandas for Data Analysis
------------------------------------------------

### Step 1: Import Libraries

Ensure you import the necessary libraries to work with Plotly and Pandas.

```python
import pandas as pd
import plotly.express as px

```

### Step 2: Load Your Dataset

Use Pandas to read your dataset into a DataFrame.

```python
df = pd.read_csv('data.csv')

```

### Step 3: Data Preparation and Analysis

Perform any necessary data cleaning,  selection,  or manipulation using Pandas functionalities.

```python
df['date'] = pd.to_datetime(df['date'])
df = df.sort_values('date')
monthly_sales = df.groupby(df['date'].dt.to_period('M')).sum().reset_index()

```

### Step 4: Create a Plotly Visualization

Generate a Plotly visualization using the prepared DataFrame. In this example,  we will create a line plot to visualize monthly sales trends.

```python
fig = px.line(
    monthly_sales,      
    x='date',      
    y='sales',      
    title='Monthly Sales Over Time',      
    labels={'date': 'Date',       'sales': 'Sales Amount'},      
    markers=True
)
fig.show()

```

### Step 5: Additional Plotly Features

Enhance your plot by adding features like hover data,  changing colors,  or adding additional traces.

```python
fig = px.line(
    monthly_sales,      
    x='date',      
    y='sales',      
    title='Monthly Sales Over Time',      
    labels={'date': 'Date',       'sales': 'Sales Amount'},      
    markers=True
)

fig.update_traces(marker=dict(color='LightSeaGreen',       size=10),       line=dict(color='DarkRed',       width=2))
fig.update_layout(title_text='Updated Monthly Sales Over Time')
fig.show()

```

### Step 6: Save the Plot

Finally,  save your Plotly graph as an HTML file for further use or sharing.

```python
fig.write_html("monthly_sales.html")

```

By integrating these steps into your project,  you can seamlessly use Plotly with Pandas to analyze and visualize data effectively.

Interactive Dashboards with Plotly Dash
---------------------------------------

In this section,  we will build an interactive dashboard using Plotly Dash. This will include creating multiple interactive components such as dropdowns,  graphs,  and layout management.

Prerequisites
-------------

Make sure you have installed Dash using the following:

![Data Mentor Advertisement](https://mentor.enterprisedna.co/)

```python
pip install dash

```

Example: Building a Sales Data Dashboard
----------------------------------------

### Step 1: Import Required Libraries

```python
import dash
from dash import dcc,       html,       Input,       Output
import plotly.express as px
import pandas as pd

```

### Step 2: Load and Prepare Your Data

For this example,  we will create a simple DataFrame to act as our data source.

```python
# Creating a sample DataFrame
data = {
    'Year': [2020,       2020,       2020,       2021,       2021,       2021],      
    'Product': ['A',       'B',       'C',       'A',       'B',       'C'],      
    'Sales': [100,       150,       200,       130,       120,       230],      
}

df = pd.DataFrame(data)
options = [{'label': i,       'value': i} for i in df['Product'].unique()]

```

### Step 3: Initialize the Dash App

```python
app = dash.Dash(__name__)

```

### Step 4: Define the Layout

Let’s define the layout where we will use a dropdown to select products and a graph to visualize sales data.

```python
app.layout = html.Div([
    html.H1('Sales Data Dashboard'),      
    dcc.Dropdown(
        id='product-dropdown',      
        options=options,      
        value='A',      
        multi=False
    ),      
    dcc.Graph(
        id='sales-graph'
    )
])

```

### Step 5: Create Callback Function

Define the callback to update the graph based on the dropdown selection.

```python
@app.callback(
    Output('sales-graph',       'figure'),      
    Input('product-dropdown',       'value')
)
def update_graph(selected_product):
    filtered_df = df[df['Product'] == selected_product]
    
    fig = px.line(filtered_df,       x='Year',       y='Sales',       
                  title=f'Sales Data for Product {selected_product}')
    
    return fig

```

### Step 6: Run the App

Finally,  run the app to start the server.

```python
if __name__ == '__main__':
    app.run_server(debug=True)

```

Now,  you have a working interactive dashboard where users can select different products from the dropdown to see their respective sales data over the years. This example can easily be expanded to include more complex data and interactions.

By integrating the concepts from earlier parts of the course (like customized plots and advanced techniques),  you can enhance the visual appeal and functionality of your dashboard.