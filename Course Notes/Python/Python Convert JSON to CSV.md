---
title: Python Convert JSON to CSV
source: https://blog.enterprisedna.co/python-convert-json-to-csv/
description:
tags:
  - csv_conversion
  - data_analysis
  - json_to_csv
  - pandas
  - python
aliases:
  - CSV conversion
  - JSON conversion
  - JSON to CSV
key_concepts:
  - CSV file format
  - Convert JSON to CSV
  - JSON file format
  - Pandas library usage
  - Python data conversion
---

# Python Convert JSON to CSV

JSON and CSV are widely used file formats for storing and exchanging data. JSON is a lightweight format that’s readable by humans and is used for transmitting data between servers and web applications,  while CSV is a plain-text format that represents tabular data with comma-separated values,  often employed for data storage in spreadsheets and databases.

**JSON to CSV conversion in Python is necessary to analyze or visualize JSON data using tabular data tools like Excel or** [**SQL databases**](https://learn.microsoft.com/en-us/sql/relational-databases/databases/databases?view=sql-server-ver16)**. Python is ideal for this task,  and by using its libraries,  you can quickly convert JSON data to a CSV file,  enabling various data analysis and visualization tasks.**

Python offers various libraries that simplify the process of converting JSON to CSV. By using these libraries,  you can complete the conversion task using just a few lines of code.

In this article,  we’ll explore the process of converting JSON to CSV using Python,  along with examples and best practices.

Let’s start by exploring some powerful JSON to CSV libraries and modules.

## **How to Convert JSON to CSV using Python Libraries**

In this section,  we’ll discuss the Python libraries and modules that can be used to convert JSON to CSV. We’ll primarily focus on the popular **pandas** library and how it can be utilized for this conversion process.

Let’s dive in!

### **Importing Pandas and Other Modules**

To begin the JSON to CSV conversion in [Python](https://blog.enterprisedna.co/python-cheat-sheet/),  you’ll first need to import the necessary libraries,  such as **pandas**.

Pandas is an open-source [data analysis and manipulation library for Python](https://blog.enterprisedna.co/python-interview-questions-for-data-engineers/),  providing data structures and functions needed to manipulate structured data. It’s especially useful for handling various data formats,  such as JSON and CSV.

### **How to Read JSON Data Using Pandas**

Once the libraries have been imported,  the next step is to read the JSON data. You can use the **pd. Read_json ()** function to convert a JSON string or file to a [pandas DataFrame](https://blog.enterprisedna.co/pandas-percentile-calculate-percentiles-of-a-dataframe/).

This function has several options to customize the resulting DataFrame,  such as specifying the file encoding or indicating whether the JSON data contains records or columns.

### **Converting DataFrame to CSV**

Once you have the JSON data in a DataFrame,  converting it to a CSV format is quite simple.

The **df. To_csv ()** method is used for this purpose,  which allows you to either return a CSV-formatted string or write the data directly to a CSV file.

In summary,  converting JSON to CSV in Python is made easy with the pandas library. The process involves importing the necessary modules,  reading the JSON data into a DataFrame,  and then converting the DataFrame to a CSV file or string.

Remember to keep the code brief and clear,  while ensuring a good understanding of the different functions and their purposes.

Check out this video tutorial on YouTube that demonstrates how to explore datasets in Python using pandas:

<iframe loading="lazy" title="How To Explore Datasets In Pandas With ProfileReport()" width="1080" height="608" src="about:blank" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen="" data-rocket-lazyload="fitvidscompatible" data-lazy-src="https://www.youtube.com/embed/SVQITfK967E?feature=oembed"></iframe>

Using pandas can be quick and easy,  but it’s not the only tool in the Python toolbox.

## Json 2 csv Library

Another option is to use the json 2 csv library,  which provides a simple command-line interface for converting JSON files to CSV format. It offers flexibility in specifying the JSON keys and CSV fields.

You can install it using pip:

After installation,  you can run the conversion using the following command:

In the next section,  we’ll take a look at how you can read and convert JSON data.

## **Reading and Converting JSON Data**

In the following section,  we are going to delve into the specifics of how to read and convert JSON data. Reading JSON data involves understanding its structure and hierarchy to extract the required information.

It’s a fundamental skill in today’s data-driven environments,  where JSON is ubiquitous,  often serving as the primary format for data exchange between web services.

### **Using read_json Function**

The **read_json** function is a powerful method for reading JSON data in Python. It allows you to easily convert JSON data into a DataFrame,  which is a tabular data structure suitable for data analysis and visualization. This function is available in the popular data manipulation library **pandas**.

[![Data Mentor Advertisement](

To use [**read_json**](https://pythonbasics.org/pandas-json/),  start by importing the pandas library:

Assuming you have a JSON data file **“data. Json”** with the following content:

You can read and convert this JSON data into CSV format using the following code:

In this example,  **pd. Read_json** reads the JSON data from the file,  and **df. To_csv** writes the resulting DataFrame to a CSV file. The **index=False** parameter ensures that the index column is not included in the CSV output.

### **How to Deal With Nested Objects**

JSON data can sometimes contain nested objects or arrays,  which can make the conversion process more complex. For instance,  consider the following JSON data:

The **city** field contains a nested object with two values: **name** and **population**. One possible way to handle this structure is to flatten the nested dictionaries into a single-level dictionary.

This can be achieved using pandas’ **json_normalize** function,  which takes a list of dictionaries or an array of JSON objects as input,  and returns a DataFrame with the nested objects flattened:

This code would create a CSV file with the following content:

Using **read_json** and handling nested objects with **json_normalize**,  you can effectively convert various JSON data structures into tabular data format (CSV) for further analysis and manipulation.

## **How to Write to CSV With Pandas**

In this section,  we’ll demonstrate how to use the pandas library to convert a JSON file to a CSV file. We’ll cover creating a [CSV](https://docs.python.org/3/library/csv.html) file,  handling null values,  and commas.

### **1. How to Create a CSV File**

To create a CSV file from a JSON file using pandas,  follow these steps:

1. Install and import the pandas library using **import pandas as pd**.
1. Load the JSON data into a pandas DataFrame using **df = pd. Read_json (“your_json_file. Json”)**.
1. Convert the DataFrame to a CSV file using **df. To_csv (“your_csv_file. Csv”,  index=False)**.

The code snippet above shows how to read a JSON file,  store its data in a DataFrame,  and then convert it to a CSV file. By setting **index=False**,  we ensure that the index from the pandas DataFrame is not written to the file.

### **2. How to Handle Null Values**

When dealing with JSON data,  it’s common to encounter null values. Pandas can handle these null values gracefully during conversion to CSV. By default,  pandas will replace any null value with the string “NaN” in the CSV file.

However,  you can specify a custom null value representation using the **na_rep** parameter:

In this example,  any null value encountered in the DataFrame will be represented as “NULL” in the final CSV file.

### **3. How to Handle Commas Within Fields**

As commas are used as delimiters in CSV files,  it’s essential to handle them properly when converting JSON to CSV.

Pandas automatically wraps any field containing a comma within double quotes. This ensures that the comma is treated as part of the field,  rather than a delimiter.

For example,  if your JSON data contains a field like **{“name”: “John,  Jane”}**,  it’ll be represented in the CSV file as **“John,  Jane”**.

When you execute this code,  it’ll create a CSV file named “output. Csv” with the following content:

To summarize,  in this section,  we covered how to:

- Convert JSON to CSV using [pandas](https://blog.enterprisedna.co/pandas-drop-index/)
- Handle null values during conversion
- Handle commas within fields

Next,  let’s take a look at how you can use this knowledge when working with real-world data.

## **How to Use JSON to CSV Conversion When Working With Real-World Data**

In this section,  we’re going to delve into the practical applications of JSON to CSV conversion,  especially when dealing with real-world data.

### **Using APIs for JSON Data**

When working with real-world data,  oftentimes,  it is useful to consume data from APIs that typically return JSON-formatted information. JSON structure involves having key-value pairs,  where keys are the attribute names and values store the actual data.

To process this data,  a script is created that connects with the API,  retrieves the necessary information,  and then handles the JSON data before converting it to a more readable format like CSV.

CSV files contain tabular data,  where each value is separated by commas,  making it easily importable into spreadsheets or data processing tools.

Converting JSON data to CSV using Python involves these steps:

1. Fetch data from the API
1. Load the JSON data to a Python [data structure](https://blog.enterprisedna.co/how-to-load-sample-datasets-in-python/) (e.g.,  a list or a dictionary)
1. Convert this data structure into a pandas DataFrame
1. Export the DataFrame as a CSV file

### **Example: Converting Employee Data to CSV**

Let’s say we have employee JSON data fetched from an API with the following keys: **id**,  **name**,  **position**,  **salary**,  and **start_date**. Our task is to create a python script that processes this data and [converts](https://blog.enterprisedna.co/bash-to-powershell-converter/) it into a CSV format. Here’s an example:

1. First,  import the necessary libraries:
1. Fetch the employee JSON data from the API:
1. Load the JSON data into a Pandas DataFrame:
1. Export the DataFrame to a CSV file:

With these steps in place,  the script would effectively convert the JSON employee data into a CSV file containing these columns: **id**,  **name**,  **position**,  **salary**,  **start_date**.

The resulting CSV data record will be easier to read and work with when analyzing employee data or processing it through other software.

## **Final Thoughts**

In this article,  we explored the process of [converting JSON to CSV using Python](https://blog.enterprisedna.co/how-to-convert-list-to-string-in-python/). We mainly focused on leveraging the Panda’s library to simplify the task and enhance efficiency. This conversion is particularly useful when dealing with large and complex JSON files.

The conversion process involves the following key steps:

1. Importing the Pandas library using **import pandas as pd**.
1. Loading the JSON data into a DataFrame using **pd. Read_json (json_string)**.
1. Converting the DataFrame to a CSV file using **df. To_csv ()** method.

By converting JSON to CSV,  we can easily import data into visualization tools such as [Tableau](https://blog.enterprisedna.co/power-bi-vs-tableau/),  [Power BI](https://blog.enterprisedna.co/18-incredible-power-bi-dashboard-examples/),  or [Python libraries](https://blog.enterprisedna.co/how-to-move-files-in-python/) like Matplotlib and Seaborn. This,  in turn,  allows us to create meaningful visualizations for better understanding and analysis.

Always ensure the accuracy of the data and the relevance of the information provided in the conversion process. Finally,  keep in mind that utilizing appropriate formatting techniques,  such as tables and bullet points,  helps in presenting the data in a more clear and understandable manner.