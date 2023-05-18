# Heta-Datain-Assignment
Assignment for the post of SQL Database Operator at Heta Datain

import pandas as pd

# Read the "data.csv" file
data_df = pd.read_csv("data.csv")
# Read the "subject.csv" file
subject_df = pd.read_csv("subject.csv")

# Display the data from "data.csv"
print("Data from data.csv:")
print(data_df.head())

# Display the data from "subject.csv"
print("Data from subject.csv:")
print(subject_df.head())

# Tranform the value2 colomn data of data.csv file by making square of values

import pandas as pd

# Read the "data.csv" file
data_df = pd.read_csv("data.csv")

# Square the values in the 'value2' column
data_df['value2'] = data_df['value2'].apply(lambda x: x**2)

# Display the transformed data
print("Transformed data:")
print(data_df.head())

# Save the data tranformed data in Mysql for both the files

import pandas as pd
import pymysql

# Read the "data.csv" file
data_df = pd.read_csv("data.csv")

# Square the values in the 'value2' column
data_df['value2'] = data_df['value2'].apply(lambda x: x**2)

# MySQL database connection details
host = 'localhost'
user = 'your_username'
password = 'your_password'
database = 'your_database_name'
table_name = 'your_table_name'

# Establish a connection to the MySQL database
connection = pymysql.connect(host=host, user=user, password=password, database=database)

# Save the transformed data to the MySQL database table
data_df.to_sql(table_name, connection, if_exists='replace', index=False)

# Close the database connection
connection.close()

print("Data saved to MySQL successfully!")

# Showcase relationship between data.csv and subject.csv file  into third file named result.csv as subject_id colomn is common between both the file  and save result.csv into database.

import pandas as pd

# Read the "data.csv" file
data_df = pd.read_csv("data.csv")
# Read the "subject.csv" file
subject_df = pd.read_csv("subject.csv")

# Merge the data frames based on the common 'subject_id' column
result_df = pd.merge(data_df, subject_df, on='subject_id')

# Save the merged data to "result.csv"
result_df.to_csv("result.csv", index=False)

# Display the merged data
print("Merged data:")
print(result_df.head())

