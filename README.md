# SQL1

PERSON TABLE

drop table if exists person;

create table person (
	person_id serial,
  name varchar(200),
  age integer,
  height integer,
  city varchar(150),
  favorite_color varchar(150)
);

insert into person (name, age, height, city, favorite_color)
values
  ('Nathan', 23, 152, 'Lehi', 'blue'),
  ('Natalie', 21, 148, 'West Jordan', 'green'),
  ('Emma', 3, 82, 'Lehi', 'pink'),
  ('Mac', 2, 71, 'American Fork', 'red'),
  ('Brigham', 1, 63, 'Pleasant Grove', 'orange');
 
 select * from person
 order by height desc; 
 
 select * from person
 order by height asc;
 
 select * from person
 order by age desc;
 
 select * from person
 where age > 20;
 
 select * from person
 where age = 18;
 
 select * from person 
 where age < 20 
 and age > 30;
  
 select * from person
 where age != 27;
 
 select * from person
 where favorite_color != 'red';
 
 select * from person
 where favorite_color != 'red' 
 and favorite_color != 'blue';
 
 select * from person
 where favorite_color = 'orange'
 or favorite_color = 'green';
 
 select * from person
 where favorite_color in('orange','green','blue');
 
 select * from person
 where favorite_color in('yellow', 'purple');
 
 ORDER TABLE
 
 drop table if exists orders;
 
 create table orders (
 	order_id serial,
   person_id integer,
   product_name varchar(300),
   product_price decimal,
   quantity integer
 );
 
 insert into orders (person_id, product_name, product_price, quantity)
 values
 (1, 'shoes', 113.50, 3),
 (2, 'chair', 218.89, 1),
 (3,'ipad', 3600.32, 6),
 (4, 'pillows', 22.16, 4),
 (5, 'hand sanitizer', 45.86, 26);
 
 
 
 select * from orders;
 
 select sum(quantity) from orders;
 
 select sum(product_price) from orders;
 
 select sum(product_price) from orders
 where person_id = 3;
 
 ARTIST TABLE
 
 insert into artist (name) 
values 
('Natalie'),
('Nate'),
('Emma');

select * from artist
order by name desc limit 10;

select * from artist
order by name asc limit 5;

select * from artist
where name like 'Black%';

select * from artist
where name like '%Black%';

EMPLOYEE TABLE

select first_name, last_name from employee
where city = 'Calgary';

select max(birth_date) from employee;

select min(birth_date) from employee;

select * from employee
where first_name = 'Nancy';

select * from employee
where reports_to = 2;

select count(*) from employee
where city = 'Lethbridge';

INVOICE TABLE

select count(*) from invoice
where billing_country ='US';

select max(total) from invoice;

select min(total) from invoice;

select * from invoice
where total > 5;

select count(*) from invoice
where total < 5;

select count(*) from invoice
where billing_state in ('CA','TX','AZ');

select avg(total) from invoice;

select sum(total) from invoice;


 
 
 
