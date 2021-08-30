# Codecademy -- New-York-Restaurants

/* reading into the data */
select * from nomnom;

/* search for the distinct neighborhood column */
select distinct neighborhood 
from nomnom;

/* search for the distinct cuisine column */
select distinct cuisine
from nomnom;

/* search for Chinese cuisine */
select * from nomnom
where cuisine = 'Chinese';

/* search for reviews that are 4 and above */
select * from nomnom
where review >= 4;

/* return restaurants that are Italian with price $$$ */
select * from nomnom
where cuisine = 'Italian' 
  and price = '$$$';

/* search for words that contain 'meatball' */
select * from nomnom
where name like '%meatball%';

/* find all the close by spots in Midtown, Downtown, and Chinatown */
select * from nomnom
where neighborhood = 'Midtown'
  or neighborhood = 'Downtown'
  or neighborhood = 'Chinatown';

/* search for all health that have empty values */
select * from nomnom
where health is null;

/* show the top 10 restaurants rank based on reviews */
select * from nomnom
order by review desc
limit 10;

/* change the rating system by case */
select review,
  case
    when review > 4.5 then 'Extraordinary'
    when review > 4 then 'Excellent'
    when review > 3 then 'Good'
    when review > 2 then 'Fair'
    else 'Poor'
  end as 'Review'
from nomnom;
