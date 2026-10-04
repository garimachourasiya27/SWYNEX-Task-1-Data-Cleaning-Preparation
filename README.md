<h1>SWYNEX – Task 1: Data Cleaning &amp; Preparation</h1>

<h2>📌 Project Overview</h2>

<p>
This project is part of the <strong>SWYNEX Data Analyst Internship – Task 1</strong>.
</p>

<p>
The objective of this task is to clean and prepare the
<strong>Cafe Sales – Dirty Data for Cleaning Training</strong> dataset using
<strong>Microsoft Excel and Power Query</strong>.
</p>

<p>
The dataset contains missing values, invalid values such as
<code>ERROR</code> and <code>UNKNOWN</code>, and inconsistent or incomplete entries.
</p>

<p>
The complete data cleaning and preparation process was performed using
<strong>Microsoft Excel and Power Query</strong> without using Python.
</p>

<hr>

<h2>📂 Dataset</h2>

<p><strong>Dataset Name:</strong> Cafe Sales – Dirty Data for Cleaning Training</p>

<p><strong>Source:</strong> Kaggle</p>

<p>
<strong>Dataset Link:</strong>
<a href="https://www.kaggle.com/datasets/ahmedmohamed2003/cafe-sales-dirty-data-for-cleaning-training">
Kaggle – Cafe Sales Dirty Data
</a>
</p>

<p>
The dataset contains <strong>10,000 rows and 8 columns</strong>.
</p>

<h3>Dataset Columns</h3>

<ul>
<li>Transaction ID</li>
<li>Item</li>
<li>Quantity</li>
<li>Price Per Unit</li>
<li>Total Spent</li>
<li>Payment Method</li>
<li>Location</li>
<li>Transaction Date</li>
</ul>

<hr>

<h2>🔎 Problems Found in the Raw Dataset</h2>

<p>Initial inspection showed the following issues:</p>

<h3>1. Missing Values</h3>

<p>Missing values were found in several columns.</p>

<table>
<thead>
<tr>
<th>Column</th>
<th>Missing Values</th>
</tr>
</thead>

<tbody>
<tr>
<td>Item</td>
<td>333</td>
</tr>
<tr>
<td>Quantity</td>
<td>138</td>
</tr>
<tr>
<td>Price Per Unit</td>
<td>179</td>
</tr>
<tr>
<td>Total Spent</td>
<td>173</td>
</tr>
<tr>
<td>Payment Method</td>
<td>2,579</td>
</tr>
<tr>
<td>Location</td>
<td>3,265</td>
</tr>
<tr>
<td>Transaction Date</td>
<td>159</td>
</tr>
</tbody>
</table>

<h3>2. Invalid Values</h3>

<p>The dataset contained invalid entries such as:</p>

<ul>
<li><code>ERROR</code></li>
<li><code>UNKNOWN</code></li>
</ul>

<p>
These values were treated as invalid/missing values during the cleaning process.
</p>

<h3>3. Data Type Issues</h3>

<p>Some columns required proper data types for analysis:</p>

<ul>
<li>Quantity → Whole Number</li>
<li>Price Per Unit → Decimal Number</li>
<li>Total Spent → Decimal Number</li>
<li>Transaction Date → Date</li>
</ul>

<hr>

<h2>🧹 Cleaning Method Used</h2>

<p>
The following cleaning steps were performed using
<strong>Microsoft Excel Power Query</strong>.
</p>

<h3>Step 1 – Replace Invalid Values</h3>

<p>
<code>ERROR</code> and <code>UNKNOWN</code> values were identified and replaced with
<code>null</code>.
</p>

<p>
This allowed the invalid entries to be handled as missing values in the next cleaning steps.
</p>

<h3>Step 2 – Convert Data Types</h3>

<p>The required columns were converted to appropriate data types:</p>

<ul>
<li><code>Quantity</code> → Whole Number</li>
<li><code>Price Per Unit</code> → Decimal Number</li>
<li><code>Total Spent</code> → Decimal Number</li>
<li><code>Transaction Date</code> → Date</li>
</ul>

<h3>Step 3 – Handle Missing Categorical Values</h3>

<p>Missing values in:</p>

<ul>
<li>Item</li>
<li>Payment Method</li>
<li>Location</li>
</ul>

<p>
were filled using the <strong>mode (most frequent value)</strong>.
</p>

<h3>Step 4 – Handle Missing Numeric Values</h3>

<p>Missing values in:</p>

<ul>
<li>Quantity</li>
<li>Price Per Unit</li>
</ul>

<p>
were filled using the <strong>median</strong>.
</p>

<p>
Median was used because it is less affected by extreme values and provides a suitable
central value for numeric data.
</p>

<h3>Step 5 – Handle Total Spent</h3>

<p>
For missing or blank <code>Total Spent</code> values, the value was calculated using:
</p>

<p>
<strong>Total Spent = Quantity × Price Per Unit</strong>
</p>

<p>
Existing valid <code>Total Spent</code> values were retained.
</p>

<h3>Step 6 – Handle Missing Dates</h3>

<p>
Invalid or missing transaction dates were handled by converting invalid values
to <code>null</code>.
</p>

<p>
Missing or blank dates were then filled using the median transaction date:
</p>

<p>
<strong>02 July 2023</strong>
</p>

<h3>Step 7 – Final Validation</h3>

<p>After cleaning:</p>

<ul>
<li>Missing and invalid values were handled</li>
<li><code>ERROR</code> and <code>UNKNOWN</code> values were replaced</li>
<li>Numeric columns contain appropriate numeric data types</li>
<li>Transaction Date is stored as a Date</li>
<li>Total Spent values are calculated correctly where required</li>
<li>Duplicate records were checked</li>
<li>The dataset is ready for further analysis</li>
</ul>

<hr>

<h2>📊 Missing Value Treatment</h2>

<table>
<thead>
<tr>
<th>Column</th>
<th>Cleaning Method</th>
<th>Final Data Type</th>
</tr>
</thead>

<tbody>
<tr>
<td>Item</td>
<td>Missing/null values replaced with Mode</td>
<td>Text</td>
</tr>

<tr>
<td>Quantity</td>
<td>Missing/null values replaced with Median</td>
<td>Whole Number</td>
</tr>

<tr>
<td>Price Per Unit</td>
<td>Missing/null values replaced with Median</td>
<td>Decimal Number</td>
</tr>

<tr>
<td>Total Spent</td>
<td>Missing/blank values calculated using Quantity × Price Per Unit</td>
<td>Decimal Number</td>
</tr>

<tr>
<td>Payment Method</td>
<td>Missing/null values replaced with Mode</td>
<td>Text</td>
</tr>

<tr>
<td>Location</td>
<td>Missing/null values replaced with Mode</td>
<td>Text</td>
</tr>

<tr>
<td>Transaction Date</td>
<td>Invalid/blank values handled using Median Date</td>
<td>Date</td>
</tr>
</tbody>
</table>

<hr>

<h2>🔄 Project Workflow</h2>

<p>The complete project workflow was:</p>

<table>
<tbody>
<tr>
<td><strong>1</strong></td>
<td>Raw Cafe Sales Dataset</td>
</tr>

<tr>
<td><strong>↓</strong></td>
<td></td>
</tr>

<tr>
<td><strong>2</strong></td>
<td>Import CSV into Microsoft Excel</td>
</tr>

<tr>
<td><strong>↓</strong></td>
<td></td>
</tr>

<tr>
<td><strong>3</strong></td>
<td>Open Data in Power Query</td>
</tr>

<tr>
<td><strong>↓</strong></td>
<td></td>
</tr>

<tr>
<td><strong>4</strong></td>
<td>Inspect Missing &amp; Invalid Values</td>
</tr>

<tr>
<td><strong>↓</strong></td>
<td></td>
</tr>

<tr>
<td><strong>5</strong></td>
<td>Replace ERROR / UNKNOWN with null</td>
</tr>

<tr>
<td><strong>↓</strong></td>
<td></td>
</tr>

<tr>
<td><strong>6</strong></td>
<td>Handle Categorical Missing Values using Mode</td>
</tr>

<tr>
<td><strong>↓</strong></td>
<td></td>
</tr>

<tr>
<td><strong>7</strong></td>
<td>Handle Numeric Missing Values using Median</td>
</tr>

<tr>
<td><strong>↓</strong></td>
<td></td>
</tr>

<tr>
<td><strong>8</strong></td>
<td>Calculate Missing Total Spent</td>
</tr>

<tr>
<td><strong>↓</strong></td>
<td></td>
</tr>

<tr>
<td><strong>9</strong></td>
<td>Handle Missing Transaction Dates using Median Date</td>
</tr>

<tr>
<td><strong>↓</strong></td>
<td></td>
</tr>

<tr>
<td><strong>10</strong></td>
<td>Set Correct Data Types</td>
</tr>

<tr>
<td><strong>↓</strong></td>
<td></td>
</tr>

<tr>
<td><strong>11</strong></td>
<td>Final Data Validation</td>
</tr>

<tr>
<td><strong>↓</strong></td>
<td></td>
</tr>

<tr>
<td><strong>12</strong></td>
<td>Cleaned Dataset</td>
</tr>

<tr>
<td><strong>↓</strong></td>
<td></td>
</tr>

<tr>
<td><strong>13</strong></td>
<td>Save Cleaned Excel File</td>
</tr>
</tbody>
</table>

<hr>

<h2>🛠️ Tools Used</h2>

<ul>
<li><strong>Microsoft Excel</strong></li>
<li><strong>Power Query</strong></li>
<li><strong>Kaggle</strong></li>
<li><strong>GitHub</strong></li>
</ul>

<hr>

<h2>📐 Final Data Types</h2>

<table>
<thead>
<tr>
<th>Column</th>
<th>Final Data Type</th>
</tr>
</thead>

<tbody>
<tr>
<td>Transaction ID</td>
<td>Text</td>
</tr>

<tr>
<td>Item</td>
<td>Text</td>
</tr>

<tr>
<td>Quantity</td>
<td>Whole Number</td>
</tr>

<tr>
<td>Price Per Unit</td>
<td>Decimal Number</td>
</tr>

<tr>
<td>Total Spent</td>
<td>Decimal Number</td>
</tr>

<tr>
<td>Payment Method</td>
<td>Text</td>
</tr>

<tr>
<td>Location</td>
<td>Text</td>
</tr>

<tr>
<td>Transaction Date</td>
<td>Date</td>
</tr>
</tbody>
</table>

<hr>

<h2>📁 Project Files</h2>

<table>
<thead>
<tr>
<th>File</th>
<th>Description</th>
</tr>
</thead>

<tbody>

<tr>
<td><code>README.md</code></td>
<td>Project documentation</td>
</tr>

<tr>
<td><code>dirty_cafe_sales.csv</code></td>
<td>Original/raw Cafe Sales dataset</td>
</tr>

<tr>
<td><code>cafe_sales_cleaned.xlsx</code></td>
<td>Final cleaned dataset prepared using Microsoft Excel and Power Query</td>
</tr>

<tr>
<td><code>cleaned_dataset_screenshot.png</code></td>
<td>Screenshot of the final cleaned dataset</td>
</tr>

<tr>
<td><code>Task-1_Data_Cleaning_Applied_Steps_1.png</code></td>
<td>Power Query Applied Steps showing the data cleaning process</td>
</tr>

<tr>
<td><code>Task-1_Data_Cleaning_Applied_Steps_2.png</code></td>
<td>Power Query Applied Steps showing additional cleaning and transformation steps</td>
</tr>

<tr>
<td><code>Task-1_Data_Cleaning_Applied_Steps_3.png</code></td>
<td>Power Query Applied Steps showing final cleaning and validation steps</td>
</tr>

</tbody>
</table>

<h3>File Description</h3>

<p>
<strong>dirty_cafe_sales.csv</strong><br>
Original Cafe Sales dataset downloaded from Kaggle. The raw dataset was kept unchanged.
</p>

<p>
<strong>cafe_sales_cleaned.xlsx</strong><br>
Final cleaned Cafe Sales dataset prepared using Microsoft Excel and Power Query.
</p>

<p>
<strong>cleaned_dataset_screenshot.png</strong><br>
Screenshot showing the final cleaned dataset after the cleaning process.
</p>

<h3>Power Query Applied Steps</h3>

<p>
The Applied Steps screenshots provide evidence of the data cleaning and transformation
process performed using Microsoft Excel Power Query.
</p>

<ul>
<li>
<code>Task-1_Data_Cleaning_Applied_Steps_1.png</code>
– Initial cleaning and transformation steps
</li>

<li>
<code>Task-1_Data_Cleaning_Applied_Steps_2.png</code>
– Missing value and data preparation steps
</li>

<li>
<code>Task-1_Data_Cleaning_Applied_Steps_3.png</code>
– Final cleaning and validation steps
</li>
</ul>

<hr>

<h2>📈 Final Result</h2>

<p>
The Cafe Sales dataset was successfully cleaned and prepared using
<strong>Microsoft Excel and Power Query</strong>.
</p>

<ul>
<li>Missing values were handled using appropriate methods</li>
<li>Invalid <code>ERROR</code> and <code>UNKNOWN</code> values were handled</li>
<li>Categorical values were imputed using Mode</li>
<li>Numeric values were imputed using Median</li>
<li>Missing Total Spent values were calculated from Quantity and Price Per Unit</li>
<li>Missing Transaction Dates were handled using the median date</li>
<li>Correct data types were applied</li>
<li>The dataset was prepared for further analysis and EDA</li>
</ul>

<hr>

<h2>🎓 Learning Outcome</h2>

<p>Through this project, I learned how to:</p>

<ul>
<li>Import and inspect a raw dataset in Power Query</li>
<li>Identify missing and invalid values</li>
<li>Replace <code>ERROR</code> and <code>UNKNOWN</code> values with null</li>
<li>Handle categorical missing values using Mode</li>
<li>Handle numeric missing values using Median</li>
<li>Create calculated values using existing columns</li>
<li>Convert columns to appropriate data types</li>
<li>Validate a cleaned dataset</li>
<li>Prepare data for further analysis</li>
<li>Document and publish a data-cleaning project on GitHub</li>
</ul>

<hr>

<h2>👩‍💻 Project Information</h2>

<table>
<thead>
<tr>
<th>Information</th>
<th>Details</th>
</tr>
</thead>

<tbody>
<tr>
<td>Internship</td>
<td>SWYNEX Data Analyst Internship</td>
</tr>

<tr>
<td>Task</td>
<td>Task 1 – Data Cleaning &amp; Preparation</td>
</tr>

<tr>
<td>Tool</td>
<td>Microsoft Excel &amp; Power Query</td>
</tr>

<tr>
<td>Dataset</td>
<td>Cafe Sales – Dirty Data for Cleaning Training</td>
</tr>

<tr>
<td>Platform</td>
<td>GitHub</td>
</tr>
</tbody>
</table>

<hr>

<h2>⭐ Conclusion</h2>

<p>
This project demonstrates the complete process of transforming a dirty Cafe Sales
dataset into a structured and analysis-ready dataset using
<strong>Microsoft Excel and Power Query</strong>.
</p>

<p>
The cleaned dataset can now be used for
<strong>Exploratory Data Analysis (EDA), visualization, and further data analysis</strong>.
</p>
