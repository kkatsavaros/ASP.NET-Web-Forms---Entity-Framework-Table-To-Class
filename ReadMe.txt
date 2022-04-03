ASP.NET Web Forms - Entity Framework Table To Class



In that project i use Entity Framework to create a class from a database table.

Entity Framework is an ORM (Object Relational Mapping).


1. Firstly i have installed Entity Framework with the NuGet Package Manager. 
   install-package EntityFramework 5.0 


2. I use database TestEntityFramework to create the tables Departments and Employees.

use TestEntityFramework;

 Create table Departments
(
     ID int primary key identity,
     Name nvarchar(50),
     Location nvarchar(50)
)

Create table Employees
(
     ID int primary key identity,
     FirstName nvarchar(50),
     LastName nvarchar(50),
     Gender nvarchar(50),
     Salary int,
     DepartmentId int foreign key references Departments(Id)
)

Insert into Departments values ('IT', 'New York')
Insert into Departments values ('HR', 'London')
Insert into Departments values ('Payroll', 'Sydney')

Insert into Employees values ('Mark', 'Hastings', 'Male', 60000, 1)
Insert into Employees values ('Steve', 'Pound', 'Male', 45000, 3)
Insert into Employees values ('Ben', 'Hoskins', 'Male', 70000, 1)
Insert into Employees values ('Philip', 'Hastings', 'Male', 45000, 2)
Insert into Employees values ('Mary', 'Lambeth', 'Female', 30000, 2)
Insert into Employees values ('Valarie', 'Vikings', 'Female', 35000, 3)
Insert into Employees values ('John', 'Stanmore', 'Male', 80000, 1)

select * from employees;

select * from departments;


3. Then i insert ADO.NET Entity Data Model and i run the wizard to make the connection with the database TestEntityFramework
   and declare which tables i want to mapping. The name of the Model Namespace is  EmployeeModel.edmx


4. Build Solution


5. Then i add a web form with a Grid view control and a EntityDataSource Control. 


6. At the EntityDataSource control i choose my connection.



Katsavaros Konstantinos



