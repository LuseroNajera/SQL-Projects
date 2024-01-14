# **Arline System** 

Table of Contents
- Purpose
- ERD 
- Creating Tables
- Inserting Data
- Select Query
- Join Query 


### Purpose
- 

### ERD - Entity Relationship Diagram
- This diagram provides a visual represntaion of the data strucsture within an arline system. With this I ahve defined the tables, fields and relationships that will be implementted in the database schema. This ERD can serve as a sort of document that can aid in future modifications and troubleshootintg. 

- ![image](https://github.com/LuseroNajera/SQL-Projects/assets/155403528/5f1fb243-2835-4e4e-847b-f68a6960f69e)


### Creating Tables 
Airplanes
- Airplane Number
- CREATE TABLE Airplane (
    Airplane_Number INT PRIMARY KEY);

Flihgt 
- flight number
- ariplane number
- CREATE TABLE Flights (
    Airplane_Number INT PRIMARY KEY,
    Flight_Number INT );

Passengers
- passenger id
- Passenger name
- flight number
- ticket mumber
- CREATE TABLE Passengers (
    Passenger_ID INT PRIMARY KEY,
    Passenger_Name VARCHAR2(100),
    Flight_Number INT,
    Ticket_Number INT,
    FOREIGN KEY (Flight_Number) REFERENCES Flight(Flight_Number)
);

Fligjt Crew
= crew name
-crew id 
- flight number
- crew position
- 10 pilots
- 30 flight attendents
- 
f
