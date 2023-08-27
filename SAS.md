---
share: true
---
# Comprehensive SAS Cheatsheet

## Basics of SAS Programming

- `data dataset_name;`: Begin a data step.
- `set data_source;`: Read data from a source.
- `input var1 var2 var3;`: Specify input variables.
- `datalines;`: Inline data input.
- `run;`: End the data step.

## Data Manipulation using SAS Data Step

- `if condition then output;`: Conditional data output.
- `retain var1 var2;`: Retain values across iterations.
- `by var1;`: Group processing by variable.
- `proc sort data=dataset; by var1; run;`: Sorting data.
- `do index = 1 to 10;`: DO loop for iteration.
- `output out=new_dataset;`: Output data to a new dataset.

## Using SAS Procedures for Analysis and Reporting

- `proc means data=dataset; var var1 var2; run;`: Descriptive statistics.
- `proc freq data=dataset; tables var1; run;`: Frequency distribution.
- `proc reg data=dataset; model var1 = var2 var3; run;`: Linear regression.
- `proc logistic data=dataset; model var1 = var2 var3; run;`: Logistic regression.
- `proc sql; SELECT var1, COUNT(*) FROM dataset GROUP BY var1; QUIT;`: SQL queries in SAS.

## Data Visualization using SAS

- `proc sgplot data=dataset; scatter x=var1 y=var2; run;`: Scatter plot.
- `proc sgplot data=dataset; histogram var=var1; run;`: Histogram.
- `proc sgplot data=dataset; vbar var1; run;`: Vertical bar chart.
- `proc sgplot data=dataset; hbar var1; run;`: Horizontal bar chart.
- `proc sgplot data=dataset; bubble x=var1 y=var2 size=var3; run;`: Bubble plot.

## Understanding SAS Libraries and Data Storage

- `libname mylib 'path_to_directory';`: Assign a library.
- `data mylib.dataset_name; set dataset; run;`: Referencing a library.
- `proc contents data=mylib.dataset_name; run;`: Display dataset contents.
- `proc datasets library=mylib; quit;`: Managing datasets in a library.
- `proc import datafile='data.csv' out=mylib.imported_data dbms=csv replace; run;`: Import external data.


