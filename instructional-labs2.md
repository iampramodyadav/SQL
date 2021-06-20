![](./instructional-labs2.md_files/IDSNlogo.png)

Hands-on Lab : COUNT, DISTINCT, LIMIT
=====================================

**Estimated time needed:** 35 minutes

In this lab, you will learn a few useful expressions that are used with SELECT statements. First, you will learn COUNT, which is an aggregate function that retrieves the number of rows that matches the query criteria. Next, you will learn DISTINCT, which is used to remove duplicate values from a specified result set and only return the unique values. Lastly, you will learn LIMIT, which is used for restricting the number of rows retrieved from the table.

Software Used in this Lab
-------------------------

In this lab, you will use [Datasette](https://github.com/simonw/datasette?utm_medium=Exinfluencer&utm_source=Exinfluencer&utm_content=000026UJ&utm_term=10006555&utm_id=NA-SkillsNetwork-Channel-SkillsNetworkCoursesIBMDeveloperSkillsNetworkDB0201ENSkillsNetwork20127838-2021-01-01), an open source multi-tool for exploring and publishing data.

Database Used in this Lab
-------------------------

The database used in this lab comes from the following dataset source: [Film Locations in San Francisco](https://data.sfgov.org/Culture-and-Recreation/Film-Locations-in-San-Francisco/yitu-d5am?utm_medium=Exinfluencer&utm_source=Exinfluencer&utm_content=000026UJ&utm_term=10006555&utm_id=NA-SkillsNetwork-Channel-SkillsNetworkCoursesIBMDeveloperSkillsNetworkDB0201ENSkillsNetwork20127838-2021-01-01) under a [PDDL: Public Domain Dedication and License](https://opendatacommons.org/licenses/pddl/1-0/?utm_medium=Exinfluencer&utm_source=Exinfluencer&utm_content=000026UJ&utm_term=10006555&utm_id=NA-SkillsNetwork-Channel-SkillsNetworkCoursesIBMDeveloperSkillsNetworkDB0201ENSkillsNetwork20127838-2021-01-01).

Objectives
----------

After completing this lab, you will be able to:

-   Retrieve the number of rows that match a query criteria
-   Remove duplicate values from a result set and return the unique values
-   Restrict the number of rows retrieved from a table

Exploring the Database
======================

Let us first explore the **SanFranciscoFilmLocations** database using the **Datasette** tool:

1.  If the first statement listed below is not already in the Datasette textbox on the right, then copy the code below by clicking on the little copy button on the bottom right of the codeblock below and then paste it into the textbox of the Datasette tool using either **Ctrl+V** or right-click in the text box and choose **Paste**.

    ``` {.code-badge-pre}
            n1ql
            
                
            
         SELECT * FROM FilmLocations;
    ```

    ![](./instructional-labs2.md_files/ExploringDB.1.png)

1.  Click **Submit Query**.

2.  Now you can scroll down the table and explore all the columns and rows of the **FilmLocations** table to get an overall idea of the table.

    ![](./instructional-labs2.md_files/ExploringDB.2.png)

1.  These are the column attribute descriptions from the **FilmLocations** table:

    ``` {.code-badge-pre}
            reasonml
            
                
            
         FilmLocations(
        Title:              titles of the films, 
        ReleaseYear:        time of public release of the films, 
        Locations:          locations of San Francisco where the films were shot, 
        FunFacts:           funny facts about the filming locations, 
        ProductionCompany:  companies who produced the films, 
        Distributor:        companies who distributed the films, 
        Director:           people who directed the films, 
        Writer:             people who wrote the films, 
        Actor1:             person 1 who acted in the films, 
        Actor2:             person 2 who acted in the films, 
        Actor3:             person 3 who acted in the films
    )
    ```

Exercise 1: COUNT
=================

In this exercise, you will first go through some examples of using COUNT in queries and then solve some exercise problems by using it.

Task A: Example exercises on COUNT
----------------------------------

Let us go through some examples of COUNT related queries:

1.  In this example, suppose we want to count the number of records or rows of the "FilmLocations" table.

    1.  Problem:

        > *Retrieve the number of rows from the "FilmLocations" table.*

    2.  Solution:

        ``` {.code-badge-pre}
                sql
                
                    
                
             SELECT COUNT(*) FROM FilmLocations;
        ```

    1.  Copy the solution code above by clicking on the little copy button on the bottom right of the codeblock below and paste it to the textbox of the Datasette tool. Then click **Submit query**.

    1.  Your output resultset should look like the image below:

        ![](./instructional-labs2.md_files/1.A.1.4.png)

1.  In this example, now we want to count the number of locations of the films. But we also want to restrict the output resultset in such a way that we only retrieve the number of locations of the films written by a certain writer.

    1.  Problem:

        > *Retrieve the number of locations of the films which are written by James Cameron.*

    2.  Solution:

        ``` {.code-badge-pre}
                sql
                
                    
                
             SELECT COUNT(Locations) FROM FilmLocations WHERE Writer="James Cameron";
        ```

    1.  Copy the solution code above by clicking on the little copy button on the bottom right of the codeblock below and paste it to the textbox of the Datasette tool. Then click **Submit query**.

    1.  Your output resultset should look like the image below:

        ![](./instructional-labs2.md_files/1.A.2.4.png)

Task B: Practice exercises on COUNT
-----------------------------------

Now, let us practice creating and running some COUNT related queries.

1.  Problem:

    > *Retrieve the number of locations of the films which are directed by Woody Allen.*

    Hint

    > Follow example 2 of the COUNT exercise. Use the WHERE clause comparison operator `=` which means **"Equal to"**.

    Solution

    ``` {.code-badge-pre}
            sql
            
                
            
         SELECT COUNT(Locations) FROM FilmLocations WHERE Director="Woody Allen";
    ```

    Output ![](./instructional-labs2.md_files/1.B.1.O.png)

1.  Problem:

    > *Retrieve the number of films shot at Russian Hill.*

    Hint

    > Follow example 2 of the COUNT exercise. Use the WHERE clause comparison operator `=` which means **"Equal to"**.

    Solution

    ``` {.code-badge-pre}
            n1ql
            
                
            
         SELECT Count(Title) FROM FilmLocations WHERE Locations="Russian Hill";
    ```

    Output ![](./instructional-labs2.md_files/1.B.2.O.png)

1.  Problem:

    > *Retrieve the number of rows having a release year older than 1950 from the "FilmLocations" table.*

    Hint

    > Follow example 1 of the COUNT exercise. Use the WHERE clause comparison operator `<` which means **"Less than"**.

    Solution

    ``` {.code-badge-pre}
            sql
            
                
            
         SELECT Count(*) FROM FilmLocations WHERE ReleaseYear<1950;
    ```

    Output ![](./instructional-labs2.md_files/1.B.3.O.png)

Exercise 2: DISTINCT
====================

In this exercise, you will first go through some examples of using DISTINCT in queries, and then solve some exercise problems by using it.

Task A: Example exercises of DISTINCT
-------------------------------------

Let us go through some examples of DISTINCT related queries:

1.  In this example, we want to retrieve the title of all films in the table in such a way that duplicates will be discarded in the output resultset.

    1.  Problem:

        > *Retrieve the name of all films without any repeated titles.*

    2.  Solution:

        ``` {.code-badge-pre}
                n1ql
                
                    
                
             SELECT DISTINCT Title FROM FilmLocations;
        ```

    1.  Copy the solution code above by clicking on the little copy button on the bottom right of the codeblock below and paste it to the textbox of the Datasette tool. Then click **Submit query**.

    1.  Your output resultset should look like the image below:

        ![](./instructional-labs2.md_files/2.A.1.4.png)

1.  In this example, we want to retrieve the count of release years of the films produced by a specific company in such a way that duplicate release years of those films will be discarded in the count.

    1.  Problem:

        > *Retrieve the number of release years of the films distinctly, produced by Warner Bros. Pictures.*

    2.  Solution:

        ``` {.code-badge-pre}
                sql
                
                    
                
             SELECT COUNT(DISTINCT ReleaseYear) FROM FilmLocations WHERE ProductionCompany="Warner Bros. Pictures";
        ```

    1.  Copy the solution code above by clicking on the little copy button on the bottom right of the codeblock below and paste it to the textbox of the Datasette tool. Then click **Submit query**.

    1.  Your output resultset should look like the image below:

        ![](./instructional-labs2.md_files/2.A.2.4.png)

Task B: Practice exercises on DISTINCT
--------------------------------------

Now, let us practice creating and running some DISTINCT related queries.

1.  Problem:

    > *Retrieve the name of all unique films released in the 21st century and onwards, along with their release years.*

    Hint

    > Follow example 1 of DISTINCT. Use WHERE clause comparsion operator `>=` which means **"Greater than or equal to"**.

    Solution

    ``` {.code-badge-pre}
            n1ql
            
                
            
         SELECT DISTINCT Title, ReleaseYear FROM FilmLocations WHERE ReleaseYear>=2001;
    ```

    Output ![](./instructional-labs2.md_files/2.B.1.O.png)

1.  Problem:

    > *Retrieve the names of all the directors and their distinct films shot at City Hall.*

    Hint

    > Follow example 1 of DISTINCT. Use WHERE clause comparsion operator `=` which means **"Equal to"**.

    Solution

    ``` {.code-badge-pre}
            n1ql
            
                
            
         SELECT DISTINCT Title, Director FROM FilmLocations WHERE Locations="City Hall";
    ```

    Output ![](./instructional-labs2.md_files/2.B.2.O.png)

1.  Problem:

    > *Retrieve the number of distributors distinctly who distributed films acted by Clint Eastwood as 1st actor.*

    Hint

    > Follow example 2 of DISTINCT. Use WHERE clause comparsion operator `=` which means **"Equal to"**.

    Solution

    ``` {.code-badge-pre}
            sql
            
                
            
         SELECT COUNT(DISTINCT Distributor) FROM FilmLocations WHERE Actor1="Clint Eastwood";
    ```

    Output ![](./instructional-labs2.md_files/2.B.3.O.png)

Exercise 3: LIMIT
=================

In this exercise, you will first go through some examples of using LIMIT in queries and then solve some exercise by using it.

Task A: Example exercises of LIMIT
----------------------------------

Let us go through some examples of LIMIT related queries:

1.  In this example, let us retrieve a specific number of rows from the top of the table in such a way that rows other than those are not in the output resultset.

    1.  Problem:

        > *Retrieve the first 25 rows from the "FilmLocations" table.*

    2.  Solution:

        ``` {.code-badge-pre}
                n1ql
                
                    
                
             SELECT * FROM FilmLocations LIMIT 25;
        ```

    1.  Copy the solution code above by clicking on the little copy button on the bottom right of the codeblock below and paste it to the textbox of the Datasette tool. Then click **Submit query**.

    1.  Your output resultset should look like the image below:

        ![](./instructional-labs2.md_files/3.A.1.4.png)

1.  In this example, let us take the first example to a more advanced level. Now we want to retrieve a specific number of rows from the table, but thid time, not from the top of the table. This time we want to retrieve a specific number of rows starting from a specific row in the table.

    1.  Problem:

        > *Retrieve the first 15 rows from the "FilmLocations" table starting from row 11.*

    2.  Solution:

        ``` {.code-badge-pre}
                n1ql
                
                    
                
             SELECT * FROM FilmLocations LIMIT 15 OFFSET 10;
        ```

    1.  Copy the solution code above by clicking on the little copy button on the bottom right of the codeblock below and paste it to the textbox of the Datasette tool. Then click **Submit query**.

    1.  Your output resultset should look like the image below:

        ![](./instructional-labs2.md_files/3.A.2.4.png)

Task B: Practice exercises on LIMIT
-----------------------------------

Now, let us practice creating and running some LIMIT related queries.

1.  Problem:

    > *Retrieve the name of first 50 films distinctly.*

    Hint

    > Follow example 1 of LIMIT. Use DISTINCT.

    Solution

    ``` {.code-badge-pre}
            n1ql
            
                
            
         SELECT DISTINCT Title FROM FilmLocations LIMIT 50;
    ```

    Output ![](./instructional-labs2.md_files/3.B.1.O.png)

1.  Problem:

    > *Retrieve first 10 film names distinctly released in 2015.*

    Hint

    > Follow example 1 of LIMIT. Use DISTINCT. Use WHERE clause comparsion operator `=` which means **"Equal to"**.

    Solution

    ``` {.code-badge-pre}
            n1ql
            
                
            
         SELECT DISTINCT Title FROM FilmLocations WHERE ReleaseYear=2015 LIMIT 10;
    ```

    Output ![](./instructional-labs2.md_files/3.B.2.O.png)

1.  Problem:

    > *Retrieve the next 3 film names distinctly after first 5 films released in 2015.*

    Hint

    > Follow example 2 of the LIMIT exercise to learn how to use OFFSET. Use DISTINCT and use the WHERE clause comparison operator `=` which means **"Equal to"**.

    Solution

    ``` {.code-badge-pre}
            n1ql
            
                
            
         SELECT DISTINCT Title FROM FilmLocations WHERE ReleaseYear=2015 LIMIT 3 OFFSET 5;
    ```

    Output ![](./instructional-labs2.md_files/3.B.3.O.png)

### Congratulations! You have completed this Lab.

### 

Author(s)
---------

-   [Sandip Saha Joy](https://www.linkedin.com/in/sandipsahajoy/?utm_medium=Exinfluencer&utm_source=Exinfluencer&utm_content=000026UJ&utm_term=10006555&utm_id=NA-SkillsNetwork-Channel-SkillsNetworkCoursesIBMDeveloperSkillsNetworkDB0201ENSkillsNetwork20127838-2021-01-01)

Other Contributor(s)
--------------------

-   

Changelog
---------

|Date|Version|Changed by|Change Description|
|:---|:------|:---------|:-----------------|
|2020-12-23|1.1|Steve Ryan|ID Review|
|2020-11-24|1.0|Sandip Saha Joy|Initial version created|

### © IBM Corporation 2020. All rights reserved.

### 

{{language}}

**
