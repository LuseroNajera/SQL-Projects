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


|Airplanes| Flight | Passengers | Flight Crew | 
|---|---|---|---|
|CREATE TABLE Airplane ( Airplane_Number INT PRIMARY KEY); | CREATE TABLE Flight (Flight_Numbe INT PRIMARY KEY, Airplane_Number INT ); | CREATE TABLE Passengers ( Passenger_ID INT PRIMARY KEY, Passenger_Name VARCHAR2(100), Flight_Number INT,Ticket_Number INT,FOREIGN KEY (Flight_Number) REFERENCES Flight(Flight_Number)); | CREATE TABLE FlightCrew (crew_id INT PRIMARY KEY, crew_name VARCHAR(255) NOT NULL, flight_number INT NOT NULL crew_position VARCHAR(50) NOT NULL, FOREIGN KEY (flight_number) REFERENCES Flight(flight_number)); | 


