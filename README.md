# World_Bank_project

create database world_bank;

select * from bank_dataset;

-- Show the country for year 2010 to 2014 and population greater than 2000
select *
from bank_dataset
where year between 2010 and 2014 and population >2000;

-- Show the electricity where the year is 2016 and the country is china 
select Access_to_electricity
from bank_dataset
where year=2016 and Country="China";

-- Show the data where the life_expectancy is not between 60 to 70
select Unemployment_rate
from bank_dataset
where life_expectancy not between 60 and 70;

-- Show the total of access to electricity in a whole number 
select round(sum(Access_to_Electricity)) as total_electricity
from bank_dataset;

-- show the total of unemployment rate and display the number in nearest multiple number (ceil)
select ceil(sum(Unemployment_rate)) as Total_emp
from bank_dataset;

-- give the average of population and give the nearest largest integer (floor)
select floor(avg(Population)) as avg_pop
from bank_dataset;

-- Divide the data year wise into 4 buckets 
select country,Year,Ntile(4) over (Order by Year)
from bank_dataset;

-- show the total of population and rank the data by ordering the country 
select Sum(Population) over (Order by Country)
from bank_dataset;

