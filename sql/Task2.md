### **Task 2.** 

#### Given the CITY and COUNTRY tables, query the names of all the continents (COUNTRY.Continent) and their respective average city populations (CITY.Population) rounded down to the nearest integer.
#### Note: CITY.CountryCode and COUNTRY.Code are matching key columns.
____

### SOLUTION

```SQL
select COUNTRY.Continent, floor(avg(CITY.Population))
from COUNTRY
join CITY
on CITY.CountryCode=COUNTRY.Code
group by COUNTRY.Continent;
```
