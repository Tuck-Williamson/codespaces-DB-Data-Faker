# CS601 - Spring 2024 - Sample data creator for the DB Project

This was copied from something I had done for an earlier assignment.

I migrated this to a codespace in case my project partners wanted to see
what the sample data generator looked like/make changes.

**Documentation**
 - [Faker](https://faker.readthedocs.io/en/stable/index.html)

## Output - Postgresql inserts to add data to our sample database.
These are unoptomized inserts. FKs are searched in each row - yeah I could optimize, 
but these are run once... so not a priority.

Output is templated with [Jinja](https://pypi.org/project/Jinja2/)
The output is of the form:
```SQL
------------------------------
-- thebestdbever.employee
------------------------------

BEGIN;            

DELETE
	FROM thebestdbever.employee
	WHERE SSN IS NOT NULL;

INSERT INTO thebestdbever.employee
	VALUES ('538578111', 'Sarah', 'Green', '2023-01-18', '4458312189', 'Busboy'),
		('398049492', 'Casey', 'Smith', '2022-01-06', '5543502978', 'Waiter'),
		('477983760', 'Marcus', 'Jensen', '2020-05-02', '1193379627', 'Hosts'),
		.
		.
		.
		('208053935', 'Lisa', 'Lee', '2020-09-13', '9394251733', 'Sommelier'),
		('051407732', 'Amber', 'Moon', '2019-05-08', '7361004618', 'Sommelier')
        ;


COMMIT;
            
------------------------------

```