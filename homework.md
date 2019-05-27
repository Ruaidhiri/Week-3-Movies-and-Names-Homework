# SQL Homework

The local cinema are having a Marvel Movie Marathon! They have asked you to help maintain their database of movies with times and attendees.

## To access the database:

First, create a database called 'marvel'

```
# terminal
createdb marvel
```

Next, run the provided SQL script to populate your database:

```
# terminal
psql -d marvel -f marvel.sql
```

Use the supplied data as the source of data to answer the questions. Copy the SQL command you have used to get the answer, and paste it below the question, along with the result they gave.

## Questions

1.  Return ALL the data in the 'movies' table.

SELECT * FROM movies;

id |                title                | year | show_time
----+-------------------------------------+------+-----------
  1 | Iron Man                            | 2008 | 15:10
  2 | The Incredible Hulk                 | 2008 | 20:45
  3 | Iron Man 2                          | 2010 | 13:15
  4 | Thor                                | 2011 | 18:55
  5 | Captain America: The First Avenger  | 2011 | 22:50
  6 | Avengers Assemble                   | 2012 | 12:35
  7 | Iron Man 3                          | 2013 | 15:35
  8 | Thor: The Dark World                | 2013 | 15:55
  9 | Batman Begins                       | 2005 | 15:40
 10 | Captain America: The Winter Soldier | 2014 | 21:00
 11 | Guardians of the Galaxy             | 2014 | 23:40
 12 | Avengers: Age of Ultron             | 2015 | 21:25
 13 | Ant-Man                             | 2015 | 23:40
 14 | Captain America: Civil War          | 2016 | 15:15
 15 | Doctor Strange                      | 2016 | 22:35
 16 | Guardians of the Galaxy 2           | 2017 | 15:55
 17 | Spider-Man: Homecoming              | 2017 | 17:40
 18 | Thor: Ragnarok                      | 2017 | 15:55
 19 | Black Panther                       | 2018 | 17:45
 20 | Avengers: Infinity War              | 2018 | 14:50

2.  Return ONLY the name column from the 'people' table

SELECT name FROM people;

name        
--------------------
George Gordon
Stephen Gossip
Simon Hall
Katherine Kerr
John McNeill
Shae Nicholsun
Rory O'Shea
Jamie Paterson
Harrison Booth
Stephanie Scullion
Patryk Smacki
Robert Tam
Michal Tyranski
Michael Urquhart
Kyle Walker
Jeremy Wood

3.  Oops! Someone at CodeClan spelled Chae's name wrong! Change it to reflect the proper spelling ('Shae Nicholsun' should be 'Chae Nicholson').

UPDATE people SET name = 'Chae Nicholson' WHERE name = 'Shae Nicholsun';

name        
--------------------
George Gordon
Stephen Gossip
Simon Hall
Katherine Kerr
John McNeill
Rory O'Shea
Jamie Paterson
Harrison Booth
Stephanie Scullion
Patryk Smacki
Robert Tam
Michal Tyranski
Michael Urquhart
Kyle Walker
Jeremy Wood
Chae Nicholson

4.  Return ONLY your name from the 'people' table.

SELECT name FROM people WHERE name = 'Rory O''Shea';

name     
-------------
Rory O'Shea
(1 row)

5.  The cinema is showing 'Batman Begins', but Batman is DC, not Marvel! Delete the entry from the 'movies' table.

DELETE FROM movies WHERE title = 'Batman Begins';

id |                title                | year | show_time
----+-------------------------------------+------+-----------
  1 | Iron Man                            | 2008 | 15:10
  2 | The Incredible Hulk                 | 2008 | 20:45
  3 | Iron Man 2                          | 2010 | 13:15
  4 | Thor                                | 2011 | 18:55
  5 | Captain America: The First Avenger  | 2011 | 22:50
  6 | Avengers Assemble                   | 2012 | 12:35
  7 | Iron Man 3                          | 2013 | 15:35
  8 | Thor: The Dark World                | 2013 | 15:55
 10 | Captain America: The Winter Soldier | 2014 | 21:00
 11 | Guardians of the Galaxy             | 2014 | 23:40
 12 | Avengers: Age of Ultron             | 2015 | 21:25
 13 | Ant-Man                             | 2015 | 23:40
 14 | Captain America: Civil War          | 2016 | 15:15
 15 | Doctor Strange                      | 2016 | 22:35
 16 | Guardians of the Galaxy 2           | 2017 | 15:55
 17 | Spider-Man: Homecoming              | 2017 | 17:40
 18 | Thor: Ragnarok                      | 2017 | 15:55
 19 | Black Panther                       | 2018 | 17:45
 20 | Avengers: Infinity War              | 2018 | 14:50

6.  Create a new entry in the 'people' table with the name of one of the instructors.

INSERT INTO people (name) VALUES ('Craig Morton');

id |        name        
----+--------------------
 1 | George Gordon
 2 | Stephen Gossip
 3 | Simon Hall
 4 | Katherine Kerr
 5 | John McNeill
 6 | Shae Nicholsun
 7 | Rory O'Shea
 8 | Jamie Paterson
 9 | Harrison Booth
10 | Stephanie Scullion
11 | Patryk Smacki
12 | Robert Tam
13 | Michal Tyranski
14 | Michael Urquhart
15 | Kyle Walker
16 | Jeremy Wood
17 | Craig Morton

7.  Harrison Booth has decided to hijack our movie evening, Remove him from the table of people.

DELETE FROM people WHERE name = 'Harrison Booth';

id |        name        
----+--------------------
  1 | George Gordon
  2 | Stephen Gossip
  3 | Simon Hall
  4 | Katherine Kerr
  5 | John McNeill
  6 | Shae Nicholsun
  7 | Rory O'Shea
  8 | Jamie Paterson
 10 | Stephanie Scullion
 11 | Patryk Smacki
 12 | Robert Tam
 13 | Michal Tyranski
 14 | Michael Urquhart
 15 | Kyle Walker
 16 | Jeremy Wood
 17 | Craig Morton

8.  The cinema has just heard that they will be holding an exclusive midnight showing of 'Captain Marvel'!! Create a new entry in the 'movies' table to reflect this.

INSERT INTO movies (title, year, show_time) VALUES ('Captain Marvel', 2019, '00:00');

id |                title                | year | show_time
----+-------------------------------------+------+-----------
 1 | Iron Man                            | 2008 | 15:10
 2 | The Incredible Hulk                 | 2008 | 20:45
 3 | Iron Man 2                          | 2010 | 13:15
 4 | Thor                                | 2011 | 18:55
 5 | Captain America: The First Avenger  | 2011 | 22:50
 6 | Avengers Assemble                   | 2012 | 12:35
 7 | Iron Man 3                          | 2013 | 15:35
 8 | Thor: The Dark World                | 2013 | 15:55
 9 | Batman Begins                       | 2005 | 15:40
10 | Captain America: The Winter Soldier | 2014 | 21:00
11 | Guardians of the Galaxy             | 2014 | 23:40
12 | Avengers: Age of Ultron             | 2015 | 21:25
13 | Ant-Man                             | 2015 | 23:40
14 | Captain America: Civil War          | 2016 | 15:15
15 | Doctor Strange                      | 2016 | 22:35
16 | Guardians of the Galaxy 2           | 2017 | 15:55
17 | Spider-Man: Homecoming              | 2017 | 17:40
18 | Thor: Ragnarok                      | 2017 | 15:55
19 | Black Panther                       | 2018 | 17:45
20 | Avengers: Infinity War              | 2018 | 14:50
21 | Captain Marvel                      | 2019 | 00:00

9.  The cinema would also like to make the Guardians movies a back to back feature. Find out the show time of "Guardians of the Galaxy" and set the show time of "Guardians of the Galaxy 2" to start two hours later.

UPDATE movies SET show_time = '01:40' WHERE title = 'Guardians of the Galaxy 2';

id |                title                | year | show_time
----+-------------------------------------+------+-----------
  1 | Iron Man                            | 2008 | 15:10
  2 | The Incredible Hulk                 | 2008 | 20:45
  3 | Iron Man 2                          | 2010 | 13:15
  4 | Thor                                | 2011 | 18:55
  5 | Captain America: The First Avenger  | 2011 | 22:50
  6 | Avengers Assemble                   | 2012 | 12:35
  7 | Iron Man 3                          | 2013 | 15:35
  8 | Thor: The Dark World                | 2013 | 15:55
 10 | Captain America: The Winter Soldier | 2014 | 21:00
 11 | Guardians of the Galaxy             | 2014 | 23:40
 12 | Avengers: Age of Ultron             | 2015 | 21:25
 13 | Ant-Man                             | 2015 | 23:40
 14 | Captain America: Civil War          | 2016 | 15:15
 15 | Doctor Strange                      | 2016 | 22:35
 17 | Spider-Man: Homecoming              | 2017 | 17:40
 18 | Thor: Ragnarok                      | 2017 | 15:55
 19 | Black Panther                       | 2018 | 17:45
 20 | Avengers: Infinity War              | 2018 | 14:50
 16 | Guardians of the Galaxy 2           | 2017 | 01:40
 21 | Captain Marvel                      | 2019 | 00:00

## Extension

1.  Research how to delete multiple entries from your table in a single command.

DELETE FROM movies WHERE title IN ('Batman Begins','Spider-Man','Ant-Man','Doctor Strange');

id |                title                | year | show_time
----+-------------------------------------+------+-----------
 1 | Iron Man                            | 2008 | 15:10
 2 | The Incredible Hulk                 | 2008 | 20:45
 3 | Iron Man 2                          | 2010 | 13:15
 4 | Thor                                | 2011 | 18:55
 5 | Captain America: The First Avenger  | 2011 | 22:50
 6 | Avengers Assemble                   | 2012 | 12:35
 7 | Iron Man 3                          | 2013 | 15:35
 8 | Thor: The Dark World                | 2013 | 15:55
10 | Captain America: The Winter Soldier | 2014 | 21:00
11 | Guardians of the Galaxy             | 2014 | 23:40
12 | Avengers: Age of Ultron             | 2015 | 21:25
14 | Captain America: Civil War          | 2016 | 15:15
16 | Guardians of the Galaxy 2           | 2017 | 15:55
17 | Spider-Man: Homecoming              | 2017 | 17:40
18 | Thor: Ragnarok                      | 2017 | 15:55
19 | Black Panther                       | 2018 | 17:45
20 | Avengers: Infinity War              | 2018 | 14:50
