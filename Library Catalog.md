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

### ERD Table 

Books
- Book_ID
- Book_Name
- Published Date
- Author_Name
Authos
- Author_Name
- Author_ID
Genres
- Genre_Name
- Book_ID
Location
- Location_Name
- Location_Address
- Book_ID
- 

### **Creating Tables** 
**Book Table**
- CREATE TABLE books (
    book_id INT PRIMARY KEY,
    published_date INT,
    title VARCHAR(255) NOT NULL,
    author_id INT,
    FOREIGN KEY (author_id) REFERENCES authors(author_id)
  );
  
**Authors Table**
- CREATE TABLE authors (
    author_id INT PRIMARY KEY,
    author_name VARCHAR(255) NOT NULL
  );
  
**Location Table**
- CREATE TABLE locations (
    location_id INT PRIMARY KEY,
    location_name VARCHAR(200) NOT NULL,
    address VARCHAR(200) NOT NULL,
    book_id INT,
    FOREIGN KEY (book_id) REFERENCES books(book_id)
  );


### **Inserting Data:** 

| Author Table | Books Table | Location Table |
|---|---|---| 
|INSERT INTO Authors VALUES (1001, 'Jessica Roux'); | INSERT INTO Books VALUES (0012, 2020, 'Floriography', 1001 ); |INSERT INTO Locations VALUES (20112, 'City Library', '123 Main St', 0012);|
|INSERT INTO Authors VALUES (1012, 'George Orwell');|INSERT INTO Books VALUES  (0013, 1945, 'Animal Farm', 1012 ); | INSERT INTO Locations VALUES (20212, 'Downtown Bookstore', '456 Tech Ave', 0013);|
|INSERT INTO Authors VALUES (1018, 'Bram Stoker');| INSERT INTO Books VALUES (0019, 1897, 'Dracula', 1018 ); |INSERT INTO Locations VALUES (20312, 'Community Center', '789 Community Blvd', 0019);|
|INSERT INTO Authors VALUES (1006, 'Ray Bradbury');| INSERT INTO Books VALUES (0043, 1953, 'Fahrenheit 451', 1006 ); | INSERT INTO Locations VALUES (20412, 'High School Library', '567 School Dr', 0043);|
|INSERT INTO Authors VALUES (1004, 'Herman Melville');| INSERT INTO Books VALUES (0023, 1851, 'Moby-Dick', 1004 ); |INSERT INTO Locations VALUES (20512, 'University Library', '567 Campus Dr', 0023);|
|INSERT INTO Authors VALUES (1010, 'William Shakespeare');| INSERT INTO Books VALUES (0039, 1597, 'Romeo and Juliet',1010 ); |INSERT INTO Locations VALUES (20612, 'Abbey Library', '394 Abbey Blvd', 0039);|
|INSERT INTO Authors VALUES (1007, 'William Golding');| INSERT INTO Books VALUES (0009, 1954, 'Lord of the Flies' ,1007 ); |INSERT INTO Locations VALUES (20712, 'Art Museum', '094 Dandy St', 0009);|
|INSERT INTO Authors VALUES (1013, 'Edgar Allan Poe');| INSERT INTO Books VALUES (0025, 1845, 'The Raven ', 1013 ); |INSERT INTO Locations VALUES (20812, 'Cypress Center', '239 Cypress Dr', 0025);|


### **SELECT Query** 

**SELECT * FROM Author;**

<img width="600" alt="image" src="https://github.com/LuseroNajera/SQL-Projects/assets/155403528/052bc85a-0e60-4008-82e2-f6c25344cc2d">

**SELECT * FROM Books;**

<img width="600" alt="image" src="https://github.com/LuseroNajera/SQL-Projects/assets/155403528/8d402098-7aff-4de6-abcc-2c96124bc032">

### **Sorting Data**
- Sorting Data by publishe date of books.  
- ![image](https://github.com/LuseroNajera/SQL-Projects/assets/155403528/a1d134de-46d4-40a2-9005-2770b2bf05b2)


### **JOIN Query**
- Retrieveing information about the books alongisde the corresponding author names. 
- ![image](https://github.com/LuseroNajera/SQL-Projects/assets/155403528/68c9ecd1-1a77-44fb-a9c5-ff856f687d82)

- Retrieving information about the locations in which the book_ID can be found. 
- ![image](https://github.com/LuseroNajera/SQL-Projects/assets/155403528/4a5e3397-ab47-4ab6-890d-82e952763cb8)










