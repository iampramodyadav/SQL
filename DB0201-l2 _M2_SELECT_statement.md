
</head>
  <body data-new-gr-c-s-check-loaded="14.987.0" data-gr-ext-installed="">
    <h2>Reading: SELECT statement examples (2 mins)</h2>
    <h2>Objectives</h2>
    <p>At the end of this lab you will be able to:</p>
    <ul>
      <li>use SELECT queries to retrieve data from the database</li>
    </ul>
    <p><b>Effort:</b> 2 min</p>
    <p>The general syntax of SELECT statments is:</p>
    <p><strong>select COLUMN1, COLUMN2, ... from TABLE1 ;</strong></p>
    <p>To retrieve all columns from the COUNTRY table we could use "*" instead of specifying individual column names:</p>
    <p><strong>select * from COUNTRY ;</strong></p>
    <p>The WHERE clause can be added to your query to filter results or get specific rows of data. To retrieve data for all rows in the COUNTRY table where the ID is less than 5:</p>
    <p><strong>select * from COUNTRY where ID &lt; 5 ;</strong></p>
    <p>In case of character based columns the values of the predicates in the where clause need to be enclosed in single quotes. To retrieve the data for the country with country code "CA" we would issue:</p>
    <p><strong>select * from COUNTRY where CCODE = 'CA';</strong></p>
    <p>In the lab that follows later in the module, you will apply these concepts and practice SELECT queries hands-on.</p>
    <p>Good luck!</p>
   
