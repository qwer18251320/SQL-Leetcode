# SQL-Leetcode
### 612. Shortest Distance in a Plane
Select Min(Round(Sqrt(Pow(p1.x-p2.x,2)+Pow(p1.y-p2.y,2)),2)) As shortest
From point_2d p1, point_2d p2
Where p1.x != p2.x OR p1.y != p2.y;

Select Min(Round(Sqrt(Pow(p1.x-p2.x,2)+Pow(p1.y-p2.y,2)),2)) As shortest
From point_2d p1 Join point_2d p2
On p1.x != p2.x OR p1.y != p2.y;

##### Power(x,y) or Pow(x,y) = x^y
##### sqrt((x1-x2)^2+(y1-y2)^2)
