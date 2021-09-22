## SQL-Leetcode
#### consecutive problems - 603. Consecutive Available Seats
##### 1. Self Join

#### Combine Tables
#### Second highest salary - 176.window function
#### Count num to find more than xxx - 596. Classes More Than 5 Students
##### need to consider duplicate - use distinct

#### Count num to calculate %, like accept rate - 597. Friend Requests I: Overall Acceptance Rate
##### can use window function: cte


## Sum(Case When...) 
## Subquert
## CTE
## Window Function: Running Total, rows, rank
### Rank() Over (Partition By category Order By...ASC|DESC) As xx
#### Sum() | Avg() | Max() | Min() - window function

###餘數 Mod(column, 2) 餘數
###(id%2 > 0) 餘數

#### Update table
Update Table.name 
Set column= Case When ...etc



####Date diff - date_sub and interval
##### Method 2. Betweem Date_sub("", interval #day) and actual day <97%>
Select activity_date As day, Count(Distinct user_id) As active_users
From Activity
Where activity_date Between Date_sub("2019-07-27", INTERVAL 29 DAY) AND '2019-07-27'
Group By activity_date;



### Bin
select "xxx" as column name, 



#### count specific / count total = percentage
##### 1173. Immediate Food Delivery I


#### Reform data formaty - use Sum(case when...)
#### Group_Concat(column)
