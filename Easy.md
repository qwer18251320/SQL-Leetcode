#### 175. Combine Two Tables
Select p1.FirstName, p1.LastName, IFNULL(a1.City,null) As City, IFNULL(a1.State,null) As State
From Person p1 Left Join Address a1 Using(PersonId);
###### Null value-regardless if there is an address for each of those people




#### 176. Second Highest Salary
##### Method 1.
With cte As
(Select*, Dense_Rank() Over (Order By Salary DESC) As rnk
 From Employee)
 
 Select Max(Salary) As SecondHighestSalary
 From cte
 Where rnk=2
 
 ##### Method 2.
 Select Max(Salary) As SecondHighestSalary
From Employee
Where Salary not in (Select Max(Salary) From Employee);
 
##### Method 3.
Select Max(Salary) As SecondHighestSalary
From Employee
Where Salary < (Select Max(Salary) From Employee);

#### 181. Employees Earning More Than Their Managers

#### 182. Duplicate Emails

#### 183. Customers Who Never Order
