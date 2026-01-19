---
title: "Temporary Table Could Not Be Re Created"
date: 2019-10-29T08:51:53+01:00
---
## Temporary tables with the same name could not be (re)  created in a procedure – a case study

A complex SQL server procedure is under development. The Developer wants to reduce the complexity, he noted that if intermediate results are populated to a staging table, the logic would be much simpler.

No worries!! He created an intermediate table on the fly. Everything work perfect. The modified code looks like the following:

Some Code:

```sql
if object_id  ( ‘temptab’) is not null
begin
drop table temptab;
end
create table  temptab( n1 int, n2 int)
```

Do the processing.

A Proof of concept is presented. Perfect on demo!

Now a similar logic is to be applied for six different sets of data within the same procedure,code snippet for each set of data would be developed by a separate developer.  The team decided to do a copy and paste of the code that is already in place.

Hmm !!! Copy and Paste !!  Anyway the table temptab is dropped and re-created each time, should not be a problem. The modified code looks like the following:

```sql
/* For first data set */
– some code
if object_id  ( ‘temptab’) is not null
begin
drop table temptab;
end
create table  temptab( n1 int, n2 int);
```

 some code in between...

```sql
/* For second data set */
if object_id (‘temptab’) is not null
begin
drop table   temptab;
end
create table temptab( n1 int, n2 int) ;
```

So far so good..

Now the Villain ( none other than the DBA ) comes into scene, he does not like the idea of dropping and recreating a permanent table from within a procedure. He preaches of N number of reasons against the practice.

What to do now ? Obvious choice – use a temporary table instead. It should be simple – code is modified as follows:

```sql
/* For first data set */
– some code
if object_id  ( ‘tempdb..#temptab’) is not null
begin
drop table #temptab;
end
create table  #temptab( n1 int, n2 int);
```

some code in between...

```sql
/* For second data set */
if object_id (‘tempdb..#temptab’) is not null
begin
drop table #temptab;
end
create table #temptab( n1 int, n2 int) ;
```

Oh No! The procedure is not getting created, It is failing with an error message

Msg 2714, Level 16, State 1, Line 10
There is already an object named ‘#temptab’ in the database.

You read it correctly, the message is -

**There is already an object named ‘#temptab’ in the database.**

Code is re-examined n number of times, not any issues were found. Logically it should drop the temporary table and re-create it, Right ? But reality is far from that ! Perplexed ?? But it was working perfectly with permanent table ! What is the problem with temporary tables?

Let us see what [Microsoft](https://docs.microsoft.com/en-us/previous-versions/sql/sql-server-2008/ms174979(v=sql.100)?redirectedfrom=MSDN) states about it:

“If more than one temporary table is created inside a single stored procedure or batch, they must have different names.”

Does it mean that we cannot re-create a temporary table from within a procedure with the same name ?  Let us check one more link –

[SQL Server Tips & Tricks](https://blogs.msdn.microsoft.com/sqlserverfaq/2012/03/15/an-interesting-find-about-temp-tables-in-sql-server/)


Crystal clear – This is a ‘feature’ by design.

If you come across a similar issue don’t waste your valuable time to resolve. Instead look for workarounds.

Thank you for visiting this post. Highly appreciate your feedback and comments.
Happy reading.



***
About the Author

**Anoo S Pillai**

Senior SQL Server DBA 

Specializing in high availibility, disaster recovery and performance tuning


