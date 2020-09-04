# Jenkins_Automation
jenkins automation with ansible, aws , docker and git

#Jenkins Automation to add sql dumb in s3 bucket with henkins job
commands used
1.create database test_db;

2.use test_db

3.create table info (name varchar(20), lastname varchar(20) age int(2));

4.insert into info values('Naveenkumar', 'Srinivasan', 24);

5.export AWS_ACCESS_KEY_ID=....
6.export AWS_SECRET_ACCESS_KEY=....

7.aws s3 cp /tmp/db.sql s3://sql-dumb-nk/dbDump

