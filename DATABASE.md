# DATABASE

```SQL
-- DROP TABLE persons
CREATE table persons 

(id INTEGER PRIMARY KEY AUTOINCREMENT, name varchar(20));
```

Primary key == the value is unique. You might want to have an ID number that is unique for a user. 
varchar == string (just a text); we can add a limitation to avoid huge amounts of input.
Autoincrement == automation of creation of numbers (new ID numbers). It is never reusing IDs. Once the ID is deleted, autoincrement takes the next available number. 
DROP table persons == when something goes wrong, you can start over

```SQL
INSERT INTO persons (name) VALUES (
  'oskars'
  );
  
select * FROM persons
```

In order to RUN only a part of the code, highlight the code you want to run, and press RUN.

ORM

%appdata% to computer search field. Find JetBrains and delete it to clear problems with IntelIJ IDEA. 
