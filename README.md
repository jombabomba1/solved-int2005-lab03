Download Link: https://assignmentchef.com/product/solved-int2005-lab03
<br>



<strong> </strong>

<strong> Subquery</strong>







<strong>Guideline for writing sub-query</strong>

<ul>

 <li>The subquery (inner query) executes once before the main query (outer query).</li>

 <li>The result of the subquery is used by the main query.</li>

 <li>Enclose subqueries in parentheses.</li>

 <li>Place subqueries on the right side of the comparison condition.</li>

 <li>Use single-row operators (&gt;, &lt;, =, &lt;=, &gt;=, &lt;&gt;) with single-row subqueries (return ONLY one value), and use multiple-row operators (IN, &gt;ANY, &gt;ALL, &lt;ANY, &lt;ALL) with multiple-row subqueries (return one or more values).</li>

 <li>A common problem with subqueries occurs when no rows are returned by the subquery. So, the main query also returns no rows.</li>

 <li>The ORDER BY clause in the subquery is NOT needed unless you are performing Top-N analysis.</li>

</ul>

<strong> </strong>

<strong>Type 1 – Nested Subquery  </strong>

○ Database evaluates the whole query in two steps:

○ First, execute the subquery (inner query).

○ Second, use the result of the subquery in the parent statement (outer query).

select customername  from customers

where creditlimit &gt; ( select creditlimit

from customers                       where customername = ‘Land of Toys Inc.’)

<strong>Type 2 – Correlated Subquery</strong>

○ Database evaluated once for each row processed by the parent statement.

○ This operation is used when a subquery refers to a column from a table in an outer query.

○ The unqualified columns in the subquery are resolved by looking in the tables named in the inner query and then in the tables named in the outer query.







select lastname  from employees e where exists (select *

from offices

where officecode = e.officecode)

<strong> </strong>

<strong>The Syntax of SELECT statement</strong>:

Documentation: <a href="https://dev.mysql.com/doc/refman/8.0/en/select.html">https://dev.mysql.com/doc/refman/8.0/en/select.html</a>




<u>Note:</u> The MySQL error code 1064 is a syntax error. This means the reason there’s a problem is because MySQL doesn’t understand what you’re asking it to do.




<u>Switch to SQL Editor</u>

– You should specify the classicmodels database before writing SQL statements using the following command:

USE db_name;




The <a href="https://dev.mysql.com/doc/refman/8.0/en/use.html">USE</a>statement tells MySQL to use the named database as the default (current) database for subsequent statements. This statement requires some privilege for the database or some object within it.

<strong> </strong>

<strong> The ER diagram for the classicmodels.</strong>

<u>    Note:</u> The MSRP is “Manufacturer’s suggested retail price” (ราคาขายปลกี แนะน าของผผู้ ลติ).

1







<strong> </strong>

<strong> </strong>

<strong>Task 1: Using the “classicmodels” database and write SQL statements to answer the following questions. </strong>




3.1 List the customer name of all customers who live in the same country of customer named “Mini Classics”. Sort the results in ascending order by customer name.

— Capture the SQL statement + Result Screen and place here




3.2 List the customer name of all customers who live in the same country of customer named “Mini Classics” and their customer names start with “Mini”.




3.3 List the product name and quantity in stock of the product that has the maximum quantities in stock.




3.4 List the order number and the total amount of sales of all orders that their total amount of sales is more than the total amount of sales order number 10103. Name the total amount of sales column to “total_amount”.




3.5 List the customer name and the employee last name of all customers that their sales rep employee worked in the office located in London city.




3.6 List all cities that are both an office location and a customer location. Remove the duplicate answer.




3.7 List all cities where customers who do not live in the same city of their sales rep employee’s office city.   Remove the duplicate answer.




3.8 List the customer name of all customers who have a credit limit greater than all average credit limits of customers in each city.




3.9 List the customer name of all customers who have a credit limit greater than their average credit limits of customers in their cities.




3.10 List the products that were never ordered by any customers.













2