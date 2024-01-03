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

| Author Table | Books Table |
|---|---|
|INSERT INTO Author VALUES (1, 'Jessica Roux'); | INSERT INTO Books VALUES (1, 'Floriography', 2020); |
|INSERT INTO Author VALUES (2, 'George Orwell');|INSERT INTO Books VALUES  (2, 'Animal Farm', 1945)); | 
|INSERT INTO Author VALUES (3, 'Bram Stoker');| INSERT INTO Books VALUES (3, 'Dracula', 1897); |
|INSERT INTO Author VALUES (4, 'Ray Bradbury');| INSERT INTO Books VALUES (4, 'Fahrenheit 451', 1953); | 
|INSERT INTO Author VALUES (5, 'Herman Melville');| INSERT INTO Books VALUES (5, 'Moby-Dick ', 1851); |
|INSERT INTO Author VALUES (6, 'William Shakespeare');| INSERT INTO Books VALUES (6, 'Romeo and Juliet ', 1597); |
|INSERT INTO Author VALUES (7, 'William Golding');| INSERT INTO Books VALUES (7, 'Lord of the Flies ', 1954); |
|INSERT INTO Author VALUES (8, 'Edgar Allan Poe');| INSERT INTO Books VALUES (8, 'The Raven ', 1845); |
|INSERT INTO Author VALUES (9, 'Larry McMurtry');| INSERT INTO Books VALUES (9, 'Lonesome Dove', 1985); |
|INSERT INTO Author VALUES (10, 'John Grisham');| INSERT INTO Books VALUES (10, 'The Godfather ', 1969);|
|INSERT INTO Author VALUES (11, 'Mario Puzo');| INSERT INTO Books VALUES (11, 'The Name of the Rose ', 1980); |
|INSERT INTO Author VALUES (12, 'Umberto Eco');| INSERT INTO Books VALUES (12, 'The Da Vinci Code ', 2003); | 
|INSERT INTO Author VALUES (13, 'Dan Brown');| INSERT INTO Books VALUES (13, 'Floriography', 2020); |
|INSERT INTO Author VALUES (14, 'Wilkie Collins');| INSERT INTO Books VALUES (14, 'The Woman in White ', 2003); |
|INSERT INTO Author VALUES (15, 'Tana French');| INSERT INTO Books VALUES  (15, 'In the Woods ', 2007); | 
|INSERT INTO Author VALUES (16, 'Anthony Horowitz');| INSERT INTO Books VALUES (16, 'Magpie Murders ', 2016); |
|INSERT INTO Author VALUES (17, 'Paula Hawkins');| INSERT INTO Books VALUES (17, 'The Girl on the Train', 2015); | 
|INSERT INTO Author VALUES (18, 'Ruth Ware'); | INSERT INTO Books VALUES (18, 'In the Dark, Dark Woods', 2015); |
|INSERT INTO Author VALUES (19, 'Tara Laskowski');| INSERT INTO Books VALUES(19, 'The Weekend Retreat ', 2023); | 
|INSERT INTO Author VALUES (20, 'Megan Lally');|INSERT INTO Books VALUES (20, 'Thats Not My Name ', 2023); |








