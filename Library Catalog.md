# **Library Catalog**     
<img width="100" alt="image" src="https://github.com/LuseroNajera/SQL-Projects/assets/155403528/1df5805e-e494-40f2-a85e-9446b3dc9573">
Note: I am using Oracle APEX to create these SQL commands and queries. 

A library catalog is a dataset on books and authors. 

## **Table of Contents**
    - Creating Tables
    - Inserting Data
    - Select Query 
    - JOIN Query 
    - Aggregate Query 
    

### **Creating Tables** 
**CREATE TABLE** Books ( 
    book_id **INT* **PRIMARY KEY**,    
    title **VARCHAR*(200),
    publication_year **INT*
);

**CREATE TABLE** Author (
    author_id **INT* **PRIMARY KEY**,    
    author_name **VARCHAR*(100)
);

Inserting Data: 
|
INSERT INTO Author VALUES (1, 'Jessica Roux');
INSERT INTO Author VALUES (2, 'George Orwell');
INSERT INTO Author VALUES (3, 'Bram Stoker');
INSERT INTO Author VALUES (4, 'Ray Bradbury');
INSERT INTO Author VALUES (5, 'Herman Melville');
INSERT INTO Author VALUES (6, 'William Shakespeare');
INSERT INTO Author VALUES (7, 'William Golding');
INSERT INTO Author VALUES (8, 'Edgar Allan Poe');
INSERT INTO Author VALUES (9, 'Larry McMurtry');
INSERT INTO Author VALUES (10, 'John Grisham');
INSERT INTO Author VALUES (11, 'Mario Puzo');
INSERT INTO Author VALUES (12, 'Umberto Eco');
INSERT INTO Author VALUES (13, 'Dan Brown');
INSERT INTO Author VALUES (14, 'Wilkie Collins');
INSERT INTO Author VALUES (15, 'Tana French');
INSERT INTO Author VALUES (16, 'Anthony Horowitz');
INSERT INTO Author VALUES (17, 'Paula Hawkins');
INSERT INTO Author VALUES (18, 'Ruth Ware');
INSERT INTO Author VALUES (19, 'Tara Laskowski');
INSERT INTO Author VALUES (20, 'Megan Lally');








