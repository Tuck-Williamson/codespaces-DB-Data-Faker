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
		('959475047', 'Kimberly', 'Manning', '2023-08-01', '9617567462', 'Busboy'),
		('975806394', 'Mitchell', 'Gallegos', '2024-03-26', '6680754056', 'Hosts'),
		('030278545', 'Taylor', 'Sanchez', '2023-07-19', '0116168401', 'Waiter'),
		('197281036', 'Katie', 'Newton', '2023-03-26', '2879135858', 'Hosts'),
		('550769928', 'Erik', 'Hicks', '2020-10-13', '9136501797', 'Bartender'),
		('086813571', 'Katie', 'Francis', '2020-05-17', '1269160962', 'Waiter'),
		('764661834', 'Kenneth', 'Smith', '2020-04-13', '0466953829', 'Waiter'),
		('000957839', 'Ryan', 'Blake', '2019-11-13', '9406389574', 'Pastry Chef'),
		('163031074', 'Robert', 'Williamson', '2023-11-28', '4965488995', 'Captain'),
		('101509746', 'Danielle', 'Baldwin', '2019-05-31', '8456848648', 'Busboy'),
		('678491178', 'Gwendolyn', 'Smith', '2020-01-12', '7815590953', 'Busboy'),
		('426599279', 'Tracie', 'Richards', '2021-11-29', '3592750874', 'Roast Chef'),
		('047106497', 'Phillip', 'Ponce', '2022-10-20', '4875262289', 'Waiter'),
		('690539364', 'Jeffrey', 'Clark', '2019-10-25', '7398054356', 'Bartender'),
		('857866246', 'Devin', 'Reed', '2022-06-02', '6976272267', 'Hosts'),
		('829336877', 'Jennifer', 'Macdonald', '2021-08-12', '3341029279', 'Captain'),
		('107057619', 'Edward', 'Avila', '2024-02-03', '5510197542', 'Hosts'),
		('310925952', 'Dana', 'Hall', '2021-11-23', '5272103045', 'Roast Chef'),
		('864461439', 'Ian', 'Jackson', '2021-03-03', '6366546472', 'Busboy'),
		('335685920', 'Kristen', 'Schneider', '2019-04-07', '4682081767', 'Captain'),
		('667106860', 'Tammie', 'Gibbs', '2020-05-02', '2393134704', 'Barback'),
		('661501191', 'Mary', 'Parker', '2023-10-14', '2896034854', 'Pastry Chef'),
		('243741337', 'Crystal', 'Bates', '2020-09-24', '8785279200', 'Waiter'),
		('493792285', 'Kelsey', 'Marquez', '2020-02-27', '9808570156', 'Waiter'),
		('779038357', 'Andrew', 'Peters', '2021-12-17', '8755703488', 'Captain'),
		('365661926', 'Monique', 'Miller', '2020-01-16', '6983965613', 'Bartender'),
		('574224455', 'Allison', 'Caldwell', '2020-04-30', '0965466610', 'Runner'),
		('603884639', 'Laura', 'Alvarez', '2019-11-19', '2859217823', 'Busboy'),
		('516295336', 'Dale', 'Schneider', '2023-10-31', '4406431156', 'Roast Chef'),
		('693361075', 'Bruce', 'Jones', '2022-04-20', '0047330720', 'Hosts'),
		('762399237', 'Erin', 'Hodges', '2023-03-14', '7722146099', 'Waiter'),
		('899056673', 'Eric', 'Richards', '2020-11-09', '7600519735', 'Waiter'),
		('797146335', 'Karl', 'Collins', '2020-03-13', '8198251925', 'Busboy'),
		('753451067', 'Jerry', 'Ellis', '2021-03-21', '7230328258', 'Hosts'),
		('466496969', 'Natasha', 'Robinson', '2022-08-15', '2252682486', 'Waiter'),
		('923604283', 'Maria', 'Huffman', '2023-06-02', '9697216418', 'Captain'),
		('719552471', 'William', 'Fields', '2021-10-06', '0370081038', 'Hosts'),
		('946166493', 'Ann', 'Chen', '2020-03-05', '6369348109', 'Pastry Chef'),
		('020390835', 'Justin', 'Taylor', '2023-01-21', '1280745383', 'Waiter'),
		('780578897', 'Aaron', 'Mcmillan', '2023-02-01', '4540541120', 'Waiter'),
		('634874902', 'Sylvia', 'Johnson', '2021-12-17', '3164155455', 'Waiter'),
		('292369692', 'Leslie', 'Elliott', '2022-03-01', '8882338726', 'Hosts'),
		('241173188', 'Melissa', 'Poole', '2020-04-21', '4707792993', 'Busboy'),
		('958387915', 'Linda', 'Abbott', '2020-07-04', '3729387223', 'Waiter'),
		('671676897', 'Daniel', 'Joseph', '2023-09-06', '9162117690', 'Waiter'),
		('915544452', 'Lindsay', 'Oliver', '2023-09-03', '9454888192', 'Waiter'),
		('897030645', 'Susan', 'Arnold', '2021-11-02', '4175310901', 'Roast Chef'),
		('673328776', 'Eric', 'Montgomery', '2019-10-22', '3093939196', 'Runner'),
		('830661617', 'Michael', 'Huerta', '2019-09-05', '7681599747', 'Waiter'),
		('314089880', 'Joyce', 'Hobbs', '2023-10-08', '6599592166', 'Bartender'),
		('367172198', 'Philip', 'Obrien', '2020-10-28', '4807378761', 'Waiter'),
		('625715792', 'Sandra', 'Krueger', '2020-03-13', '8809275935', 'Waiter'),
		('847791599', 'Stacy', 'Lee', '2023-06-30', '1240657200', 'Roast Chef'),
		('694170809', 'Elizabeth', 'Brown', '2022-11-03', '4415830602', 'Waiter'),
		('038756607', 'Kristina', 'Williams', '2023-04-24', '4471728134', 'Waiter'),
		('573300002', 'Andrew', 'Jordan', '2023-01-03', '1132596703', 'Barback'),
		('852768063', 'John', 'Farley', '2023-04-25', '5230922542', 'Sous Chef'),
		('737172266', 'Stephanie', 'Mckay', '2024-01-10', '4384195319', 'Bartender'),
		('546170244', 'Anthony', 'Combs', '2019-08-28', '1911660952', 'Waiter'),
		('189270701', 'Wanda', 'Jones', '2021-08-04', '1019340009', 'Bartender'),
		('734467274', 'Stephanie', 'Scott', '2023-04-06', '5072165188', 'Roast Chef'),
		('140503013', 'Rachel', 'Parker', '2021-04-12', '3667317200', 'Back Waiter'),
		('896718558', 'Brandon', 'Reeves', '2022-05-22', '8160026639', 'Captain'),
		('889663120', 'Robert', 'Boyle', '2022-12-12', '6366812553', 'Sous Chef'),
		('541776713', 'Cathy', 'Campbell', '2023-02-20', '3812953367', 'Captain'),
		('430290101', 'Mark', 'Wise', '2021-05-04', '7877868651', 'Waiter'),
		('716051893', 'James', 'Lindsey', '2022-02-17', '7033397170', 'Captain'),
		('920721812', 'Veronica', 'Palmer', '2021-10-12', '4437090301', 'Sous Chef'),
		('982937827', 'Katherine', 'Norton', '2020-09-08', '8645678902', 'Back Waiter'),
		('986341022', 'Andrew', 'Lee', '2023-10-17', '0937628761', 'Barback'),
		('351060262', 'Steven', 'Chen', '2023-12-09', '4060002494', 'Hosts'),
		('871778585', 'Michael', 'Martinez', '2020-09-27', '6270643250', 'Roast Chef'),
		('495265793', 'Christopher', 'Dominguez', '2019-12-20', '0863667098', 'Captain'),
		('142230207', 'Angela', 'Herrera', '2023-12-03', '2210623048', 'Captain'),
		('895219321', 'Clifford', 'Martinez', '2022-04-23', '4866709959', 'Roast Chef'),
		('879371154', 'Keith', 'King', '2020-09-17', '8878075434', 'Waiter'),
		('240565931', 'Megan', 'Anderson', '2020-08-24', '7749177004', 'Waiter'),
		('558329350', 'Kendra', 'Lopez', '2023-10-24', '9497536397', 'Roast Chef'),
		('153848194', 'Janet', 'Cooley', '2023-11-08', '6755833377', 'Roast Chef'),
		('176612259', 'Robert', 'Brown', '2021-03-14', '9115476355', 'Captain'),
		('088908934', 'Edwin', 'Mendoza', '2022-08-25', '7805803597', 'Busboy'),
		('076989540', 'Jeff', 'Brown', '2023-09-16', '4659797366', 'Waiter'),
		('511410913', 'Tara', 'Thompson', '2020-05-20', '4757825641', 'Waiter'),
		('578436809', 'Robert', 'Wilson', '2023-08-28', '7941144547', 'Bartender'),
		('505667920', 'Richard', 'Williams', '2021-03-16', '8639292994', 'Roast Chef'),
		('528625759', 'Edward', 'Church', '2020-12-31', '6354769750', 'Roast Chef'),
		('046985780', 'Charles', 'Wilson', '2020-12-31', '7354128388', 'Roast Chef'),
		('532753497', 'Patrick', 'Newton', '2019-12-23', '1919979697', 'Executive Chef'),
		('688388489', 'George', 'Yu', '2021-10-23', '5037319381', 'Manager'),
		('212884559', 'Jeffery', 'Meyer', '2022-03-23', '4940242597', 'Manager'),
		('845993205', 'Andrew', 'Graves', '2020-07-17', '4201530006', 'Manager'),
		('045312244', 'Katherine', 'Henderson', '2023-07-25', '1816351171', 'Manager'),
		('748438907', 'Shawn', 'Park', '2019-06-10', '7944897595', 'Sommelier'),
		('208053935', 'Lisa', 'Lee', '2020-09-13', '9394251733', 'Sommelier'),
		('051407732', 'Amber', 'Moon', '2019-05-08', '7361004618', 'Sommelier')
        ;


COMMIT;
            
------------------------------

```