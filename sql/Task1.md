### **Task 1.** 

#### Given the CITY and COUNTRY tables, query the names of all cities where the CONTINENT is 'Africa'.
#### Note: CITY.CountryCode and COUNTRY.Code are matching key columns.
____

### SOLUTION

```SQL
select city.name 
from city, country 
where code=countrycode and continent='Africa';
```
