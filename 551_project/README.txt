For NoSQL database management system:
Including db1.py, commands.py

First run commands.py which is command line interface at terminal 

Command: create_database database_name
Sample: create_database sample

Command: create_table table_name column1 type1, column2 type2...
Sample: create_table books author str, year int
Sample: create_table book bid int, author str, year int
Sample: create_table person id int, name str, age int

Command: delete_table table_name
Sample: delete_table books

Command: insert_row table_name {column1: value1, column2: value2...}
Sample: insert_row book {'bid': 1, 'author': 'Tom', 'year': 2000}
Sample: insert_row book {'bid': 2, 'author': 'David', 'year': 2010}
Sample: insert_row person {'id': 1, 'name': 'Tom', 'age': 45}
Sample: insert_row person {'id': 2, 'name': 'Tom', 'age': 20}
Sample: insert_row person {'id': 3, 'name': 'Jerry', 'age': 22}
Sample: insert_row person {'id': 4, 'name': 'xx', 'age': 22}

Command: delect_row tablename key operator value
Sample: delete_row person name == xx

Command: update_row tablename key operator value to new_value
Sample: update_row person name == Jerry to David

Command: show_data table_name
Sample: show_data person
#There will be questioned to ask you set limit, condition, specified columns. If you don’t need, just input no.

Command: ordering_data table_name new_table_name column True/False
Sample: ordering_data person order_person age False
#Using show_data to see the result 
show_data order_person

Command: min table_name new_table_name min_column
Sample: min person min_person age 
#Using show_data to see the result 
show_data min_person

Command: max table_name new_table_name max_column
Sample: max person max_person age
#Using show_data to see the result 
show_data max_person

Command: count table_name new_table_name
Sample: count person count_person
#Using show_data to see the result
show_data count_person

Command: sum table_name new_table_name column_name
Sample: sum person sum_person age
#Using show_data to see the result
show_data sum_person

Command: avg table_name new_table_name avg_column
Sample: avg person avg_person age
#Using show_data to see the result
show_data avg_person

Command: groupby table_name new_table_name groupby_column
#After groupby command, the code will ask if you need aggregation function. If you don’t need it, input no. if you need it, imput second part command
Sample: groupby person group_person name           	min age min_tb
Sample: groupby person group_person name           	max age max_tb
Sample: groupby person group_person name      	sum age sum_tb
Sample: groupby person group_person name      	avg age avg_tb
Sample: groupby person count_person name      	count count_tb

Command: join table1_name table2_name new_table_name table1_join_column table2_join_column
Sample: join person book p_b name author
#Using show_data to see the result
show_data p_b





For relational database management system:
Including MyRelationalDatabase.py, myQuery.py

Getting Started
Start the Application: Run python myQuery.py in your terminal to start the application.

Basic Commands
Create a Database:

create_database MyDatabaseTest551 creates a new database named MyDatabaseTest551.
Create a Table:

create_table Customers CustomerID int, Name str, Location str creates a table named Customers with specified columns.
Inserting Rows:

insert_row Customers {"CustomerID": 1, "Name": "Alice", "Location": "New York"} adds a new row to the Customers table.
Displaying Data:

show_data Customers displays data from the Customers table.
Follow prompts to filter or limit the data displayed.
Joining Tables:

JOIN: join Customers Orders JoinTable CustomerID CustomerID creates a joined table from Customers and Orders.
Ordering Data:

ordering_data Customers CustomersOrderedbyName Name False orders Customers by Name in descending order.
Counting Rows:

count Customers CountCustomers Name counts the number of customers.


Some Examples:
python myQuery.py

db> create_database MyDatabaseTest551

db> create_table Customers CustomerID int, Name str, Location str

db> insert_row Customers {"CustomerID": 1, "Name": "Alice", "Location": "New York"}
db> insert_row Customers {"CustomerID": 2, "Name": "Bob", "Location": "Los Angeles"}
db> insert_row Customers {"CustomerID": 3, "Name": "Charlie", "Location": "Chicago"}
db> show_data Customers

db>show> How many rows do you want to present? (type an interger/no): 3

db>show> Any request on selection of data? (e.g. year_of_manufacture > 2022/no): Name == Alice

db>show> Specify columns? (cloumns separated by comma/no): no
{'CustomerID': 1, 'Name': 'Alice', 'Location': 'New York'}

db> show_data Customers
db>show> How many rows do you want to present? (type an interger/no): no
db>show> Any request on selection of data? (e.g. year_of_manufacture > 2022/no): no
db>show> Specify columns? (cloumns separated by comma/no): Name,Location
{'Name': 'Alice', 'Location': 'New York'}
{'Name': 'Bob', 'Location': 'Los Angeles'}
{'Name': 'Charlie', 'Location': 'Chicago'}

create_table Orders OrderID int, CustomerID int, Product str, Quantity int
insert_row Orders {"OrderID": 100, "CustomerID": 1, "Product": "Laptop", "Quantity": 1}
insert_row Orders {"OrderID": 101, "CustomerID": 2, "Product": "Smartphone", "Quantity": 2}
insert_row Orders {"OrderID": 102, "CustomerID": 3, "Product": "Tablet", "Quantity": 1}

show_data Customers
show_data Orders

JOIN: join Customers Orders JoinTable CustomerID CustomerID


show_data JoinTable

ordering_data Customers CustomersOrderedbyName Name False

show_data CustomersOrderedbyName

count Customers CountCustomers Name

show_data CountCustomers





For web interface:

Including app.py, index.html, interface.html, results.html in folder templates
Modified db1.py, cc.py for nosql db
Modified myQuery.py, MyRelationalDatabase.py for relational db

Getting Started
To run all the files in a project type in your terminal:
FLASK_ENV=development
flask run --debugger --reload

Click the link showed in your terminal

Choose database by clicking the button

Input your commands in the box and click execute