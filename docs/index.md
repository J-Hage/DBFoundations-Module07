User Defined Functions
Author: Jourieh Hage*
Date: Nov. 29, 2021*

Introduction 
In this paper we will learn about SQL (Structured Query Language) User Defined Functions (UDFs), what they are, and when we would use them. In addition, we will look at the differences between Scalar, Inline, and Multi-Statement functions.  

User Defined Functions 
SQL has a variety of built-in functions, such as aggregate, analytic, ranking, conversion, and more. SQL also allows us to create custom functions known as User Defined Functions (UDFs). Two types of UDFs are: functions that return a single value and functions that return a table of values.  

UDFs are used for several different reasons, including standard programming and faster execution. Once we create a UDF function, it is stored in the database and we can use it in other coding throughout our database. UDFs create faster execution as they do not have to be reoptimized every time a UDF is run since it has already been saved in the database. Finally, UDFs can filter down data by using WHERE clauses that reduce the amount of data returned in the report.  

Scalar Functions 
Scalar function is one type of UDF. Scalar functions return as an expression a single data value such as a string of text, a number, or a date. Parameters within the scalar function can define the type of data returned. Scalar functions can accept a number of parameters but return only one value.  

As shown in Figure 1: Scalar Functions, the function ‘dbo.MultiplyValues’ was created to take the expression of ‘value 1’ multiplied by ‘value 2’ to return a single value. Then, when applied into a SELECT statement the function returns only the ‘Extended Price’ values in the result set.  

<img src="https://github.com/J-Hage/DBFoundations-Module07/tree/main/docs/Fig1.png" alt="Figure 1: Scalar Functions" width="500" height="600">

Inline Functions 
Inline functions are another type of UDF. Inline functions return the result set as a table. As with scalar functions, inline functions can accept a number of parameters. In contrast to scalar functions, inline functions return a table set of results.  

As shown in Figure 2: Inline Functions, the function ‘fnFilmsByDuration’ returns a table of results with the parameter of the ‘FilmRunTimeMinutes’ being greater than or equal to a specified value. When the function is applied in a SELECT statement specifying the parameter to be 190 minutes, it returns a table result of all the films with run times greater than or equal to 190 minutes.  

<img src="https://github.com/J-Hage/DBFoundations-Module07/tree/main/docs/Fig2.png" alt="Figure 2: Inline Functions. Inline and Multi-Statement Table Valued Functions (External Site) " width="500" height="600">
 
Multi-Statement Function 
Multi-Statement functions are a third type of UDF.  Similar to inline functions, multi-statement functions also return a table of results. However, in contrast to inline functions, multi-statement functions require additional processing of a temporary table that is directly constructed in the script.  

As shown in Figure 3: Multi-Statement Functions, the function ‘fnPeopleBornYear’ has a parameter defined as ‘@BirthYear’. The output of the function is established in a temporary table ‘@people’, where the structure of the table and data types are defined. Next, the function begins by inserting the correct data. When the function is applied in a SELECT statement, specifying the parameter to be the birth year of 1945, it returns a table result showing all actors and directors born in the year 1945. 

<img src="https://github.com/J-Hage/DBFoundations-Module07/tree/main/docs/Fig2.png" alt="Figure 3: Multi-Statement Functions . Inline and Multi-Statement Table Valued Functions (External Site) " width="500" height="600">

Summary 
In summary, UDFs are customized functions that can have parameters which return a single value or a table of results. A scalar function returns a single value. An inline function returns a table set of results. Finally, a multi-statement function also returns a table set of results but uses a temporary table constructed within the function to return the complex results. 

 

Page Break
References 


Root, Randy. Professor at University of WA. Teaching Foundations of Databases & SQL Programming course.  

 

Scalar UDF Inlining. (n.d.) Microsoft SQL Docs. Retrieved from external site.  

https://docs.microsoft.com/en-us/sql/relational-databases/user-defined-functions/scalar-udf-inlining?view=sql-server-ver15 (External Site Link). 

 

Wise Owl Training. Inline and multi-statement table-valued functions Blog. (n.d.) Retrieved from external site. https://www.wiseowl.co.uk/blog/s347/table-valued-functions.htm (External Site Link). 
