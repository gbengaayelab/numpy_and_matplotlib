# Using Numpy Arrays and Matplotlib For Data Explorations

This repository contains an example of using NumPy arrays and Matplotlib to perform data analysis and visualization. 

## Prerequisites
To run the code in this repository, you will need to have the following Python libraries installed on your system:
- NumPy
- Pandas
- Matplotlib

## Code Description
The code in this repository demonstrates how to perform the following tasks using NumPy arrays and Matplotlib:

1. Sort an array in descending order
2. Create a DataFrame from NumPy arrays
3. Concatenate DataFrames
4. Create and customize pie charts
5. Create and customize bar charts
6. Create and customize line charts
7. Generate and manipulate NumPy arrays

## Usage
The code in this repository is provided as a Python file named `numpy_matplotlib.py`. To use it, simply open the file in a Python environment and run it. 

## Example
```python
import numpy as np
import pandas as pd
import matplotlib.pyplot as pl

# Create a NumPy array of salaries
salary = [6000, 90000, 30000, 40000, 60000, 10000, 55000, 40000]
salary.sort(reverse=True)
salary = np.array(salary)

# Create a NumPy array of staff names
staff_name = np.array(['Abel', 'Tom', 'Sam', 'Juliana', 'Mark', 'Stev', 'Roslin', 'Gracie'])

# Create a DataFrame from the NumPy arrays
staff_name_dframe = pd.DataFrame(staff_name, columns=['Staff Name'])
salary_dframe = pd.DataFrame(salary, columns=['Staff Salary'])
staff_records = pd.concat([staff_name_dframe, salary_dframe], axis= 1)

# Sort the staff records by name in descending order
staff_records.sort_values(by=['Staff Name'], ascending=False)

# Create a pie chart to visualize the salaries
new_label = []
for each_item in range(len(salary)):
    new_label.append(str(staff_name[each_item]) + ':\n£' + str(salary[each_item]))
pl.pie(salary, labels=new_label, counterclock=False, startangle=90, labeldistance= 1.3, radius=2, rotatelabels=True )
pl.show()

# Create a bar chart to visualize the salaries
pl.bar(staff_name, salary, color=(0, 0.6, 0.4, 0.9),  width=0.5)

# Create a line chart to visualize the relationship between profit, COGS, and sales
profit = [40040, -20000, 30000, 20000, 10000]
profit_arr = np.array(profit)
cogs = [21000, 50000, 40010, 10000, 45000]
cogs_arr = np.array(cogs)
sales = [50000, 100000, 106000, 50000, 65000]
sales_arr = np.array(sales)
pl.plot(profit, cogs)
pl.plot(profit, sales)
pl.legend(['cogs', 'sales'])
pl.title('Relationship Between Profit COGS and Sales at Profit Points')
pl.ylabel('COGS and Sales in £')
pl.xlabel('Profit in £')
pl.show()

# Generate and manipulate a NumPy array
points = np.arange(0, 3*np.pi, 0.1)
```

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.