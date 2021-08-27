#### 175. Combine Two Tables
##### Select p1.FirstName, p1.LastName, IFNULL(a1.City,null) As City, IFNULL(a1.State,null) As State
##### From Person p1 Left Join Address a1 Using(PersonId);
###### Null value-regardless if there is an address for each of those people
