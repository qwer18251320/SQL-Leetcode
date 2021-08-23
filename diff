# 1709. Biggest Window Between Visits
Select user_id, max(window1) As biggest_window
From
(Select user_id,
 Abs(Datediff(visit_date, IfNull(lead(visit_date) over(partition by user_id order by visit_date), "2021-1-1"))) As window1
From UserVisits) As t1    
group by user_id
order by 1;

#1949. Strong Friendship
With cte As 
(Select user1_id, user2_id from Friendship
 Union
 Select user2_id, user1_id from Friendship) #friendship list

Select c1.user1_id As user1_id, c2.user1_id As user2_id, Count(*) As common_friend
From cte c1 Join cte c2
On c1.user2_id = c2.user2_id 
And c1.user1_id < c2.user1_id
Where (c1.user1_id, c2.user1_id) In (Select* From cte)
Group By 1,2
Having Count(*)>=3;


# 1843. Suspicious Bank Accounts
# condition 1  total income exceeds the max_income for this account for two or more consecutive months
# condition 2  total income of an account in some month is the sum of all its deposits in that month

With cte As
(Select t1.account_id, DATE_FORMAT(day,'%Y%m') As month, Sum(amount) As total_income, max_income
From transactions t1 Left Join Accounts Using(account_id)
Where t1.type="Creditor"
Group By t1.account_id, DATE_FORMAT(day,'%Y%m')
Having Sum(amount)>max_income)

Select c1.account_id
From cte c1, cte c2
Where c1.account_id = c2.account_id
And PERIOD_DIFF(c1.month, c2.month)=1
Group By c1.account_id
Order By c1.account_id;

#DATE_FORMAT(day,'%Y%m')
#PERIOD_DIFF(t1.date, t2.date)=1

#1934. Confirmation Rate
Select s1.user_id, Round(IfNull(Sum(Case When action = "confirmed" Then 1 Else 0 End)/Count(*),0),2) As confirmation_rate
From Signups s1 Left Join Confirmations Using(user_id)
Group By s1.user_id;

#難點 user_id 6 所以要left join 抓s1 user_id

#1841. League Statistics
select
    team_name
    , count(*) as matches_played
    , sum(case when home > away then 3 when home = away then 1 else 0 end) as points
    , sum(home) as goal_for
    , sum(away) as goal_against
    , sum(home) - sum(away) as goal_diff
    
from 
    (select home_team_id, home_team_goals as home, away_team_goals as away from matches
     union all
     select away_team_id as home_team_id, away_team_goals as home, home_team_goals as away from matches
	 ) g
join teams t on g.home_team_id = t.team_id
group by 1
order by 3 desc, 6 desc, 1


#1555. Bank Account Summary
Select USER_ID, USER_NAME, IfNull(Sum(Case When u1.user_id=t1.paid_by Then -amount Else amount End),0)+credit As CREDIT,
(Case When IfNull(Sum(Case When u1.user_id=t1.paid_by Then -amount Else amount End),0)+credit< 0 Then "Yes" Else "No" End) As CREDIT_LIMIT_BREACHED
From Users u1 Left Join Transactions t1
On u1.user_id = t1.paid_by 
Or u1.user_id = t1.paid_to
Group By u1.user_id;
# 難點: user_id 4
