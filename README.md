# MariaDB -- MySQL
This repository consists of the basics of MySQL(using MariaDB) on Linux Operating System(CentOS). MariaDB is a community-developed, commercially supported fork of the MySQL relational database management system, intended to remain free and open-source software under the GNU GPL. This repository focusses on '__SQL__' and not 'NoSQL'.

## What is a database?
A database is an organized collection of data, generally stored and accessed by firing certain queries(commands) from an computer system.

## Starting MariaDB
On terminal do the following:

    $ sudo systemctl start mariadb.service

You'll be prompted for the password to start mariadb service. To check its status:

    $ systemctl status mariadb.service
   
You will get something like this
![alt text](https://github.com/samuelpio01/mariadb-mysql/blob/master/mariadb-status.png)

If you get this it means that the MariaDB service is running. 

Incase you get an Error due to firewall you can disable the firewall by using the following command:

To check status of firewall: 
    
    sudo systemctl status firewalld
    
To stop firewall: 

    sudo systemctl stop firewalld

Next, it's time to log in into the database.

    $ mysql -u username -p

You will be prompted to enter the passoword for the database. After you enter the password you know you are into MariaDB when you see the following below. 
    
    MariaDB [(none)]> 
    
The [(none)] means that you are not using any database (we don't have one yet!). Let's create one.

## Using MariaDB
Create database:

    MariaDB [(none)]> create database db_name;
    
See all existing databases:

    MariaDB [(none)]> show databases;

Use created database:

    MariaDB [(none)]> use db_name;
    
Creating a table into the database:

Let's create a Employee table with the following coloumns : ID -> Integer which will be a primary key(cannot have duplicate ID's) and auto increment, Name -> String(varchar), Department -> String(varchar), Salary -> Float.

    MariaDB [(db_name)]> create table employee(id int auto_increment primary key,name varchar(20), department varchar(20), salary float);

Table name created is __'employee'__.

Adding an entry into the table:

     MariaDB [(db_name)]> insert into employee(id, name, department, salary) values(1,"James Borges","Electronics",58000.0);

All strings (varchar) should be entered into double quotes. 

We can also make an entry by the following:

    MariaDB [(db_name)]> insert into employee(name, department, salary) values("James Borges","Electronics",58000.0);
    
Even if the ID is not entered it will automatically be incremented by 1 from the highest ID in the table. If we do not enter a value for any column it will by default be taken as 'null' for that cell.

To see the full table:

    MariaDB [(db_name)]> select * from employee

 * means select all columns
 
 Syntax for printing:
 
    select column_name from table_name
    
when column name is * it will print all the columns.

Output will be a list of entries into the table:
![alt text](https://github.com/samuelpio01/mariadb-mysql/blob/master/mariadb-table-print.png)

If we want to print a particular column (say salary column):

    select salary from table_name;

![alt text](https://github.com/samuelpio01/mariadb-mysql/blob/master/salary_column.png)

If you want to print multiple columns then write each column with a comma in between in place of column name.


Using the 'where' clause:

.....//..... to be filled
