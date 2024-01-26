# **Arline System** 

Table of Contents
- [Purpose](#Purpose)
- [ERD](#ERD) 
- [Tables](#Tables)
- [Queries](#Queries)
- PL/SQL Queries 


### Purpose
- 

### ERD 
Entity Relationship Diagram
- This diagram provides a visual represntaion of the data strucsture within an arline system. With this I ahve defined the tables, fields and relationships that will be implementted in the database schema. This ERD can serve as a sort of document that can aid in future modifications and troubleshootintg. 

- ![image](https://github.com/LuseroNajera/SQL-Projects/assets/155403528/5f1fb243-2835-4e4e-847b-f68a6960f69e)


### Tables 


| **Airplanes** | **Flight** | **Passengers** | **Flight Crew** | 
|---|---|---|---|
|CREATE TABLE Airplane ( Airplane_Number INT PRIMARY KEY); | CREATE TABLE Flight (Flight_Numbe INT PRIMARY KEY, Airplane_Number INT ); | CREATE TABLE Passengers ( Passenger_ID INT PRIMARY KEY, Passenger_Name VARCHAR2(100), Flight_Number INT,Ticket_Number INT,FOREIGN KEY (Flight_Number) REFERENCES Flight(Flight_Number)); | CREATE TABLE FlightCrew (crew_id INT PRIMARY KEY, crew_name VARCHAR(255) NOT NULL, flight_number INT NOT NULL crew_position VARCHAR(50) NOT NULL, FOREIGN KEY (flight_number) REFERENCES Flight(flight_number)); | 

### Queries

**Passenger Details with Flight Information**
| QUERY | OUTPUT |
|----|------|
|SELECT <br/> P.Passenger_ID,<br/> P.Passenger_Name,<br/> P.Flight_Number,<br/> P.Ticket_Number,<br/> F.Airplane_Number <br/> FROM Passengers <br/> PJOIN Flight F <br/> ON P.Flight_Number = F.Flight_Number; | ![Screenshot 2024-01-18 183121](https://github.com/LuseroNajera/SQL-Projects/assets/155403528/1d969add-8ae0-499d-9c07-cc2d668a09a2) | 



**Total Passengers on Each Flight**
| QUERY | OUTPUT |
|---|---|
| SELECT <br/> Flight_Number, <br/>COUNT(*) AS total_passengers <br/>FROM Passengers <br/>GROUP BY Flight_Number;  | ![image](https://github.com/LuseroNajera/SQL-Projects/assets/155403528/641c979a-01e1-4f9e-994a-ebe0b7e43574) |


**Flights with Co-Pilots**
| QUERY | OUTPUT |
|---|---|
| SELECT <br/>P.Flight_Number, <br/>FC.crew_id,<br/>FC.crew_name, <br/>FC.crew_position <br/>FROM Passengers <br/>PJOIN FlightCrew FC ON P.Flight_Number = FC.flight_number AND FC.crew_position = 'Co-Pilot'; | ![image](https://github.com/LuseroNajera/SQL-Projects/assets/155403528/e67a91d6-f5bb-4611-a854-6e7b887ae47b) | 

  
**Counting Crew Members on each flight**
| QUERY | OUTPUT |
|---|---|
| SELECT <br/>F.Flight_Number, <br/> COUNT(CASE WHEN FC.crew_position = 'Pilot' THEN 1 END) AS num_pilots, <br/>COUNT(CASE WHEN FC.crew_position = 'Co-Pilot' THEN 1 END) AS num_co_pilots, <br/>COUNT(CASE WHEN FC.crew_position = 'Flight Attendant' THEN 1 END) AS num_flight_attendants<br/>FROM Flight <br/>FJOINFlightCrew FC ON F.Flight_Number = FC.flight_number <br/>GROUP BY F.Flight_Number; | ![image](https://github.com/LuseroNajera/SQL-Projects/assets/155403528/23dbf1fa-f4b5-43bc-83e6-db937eb5ffb6) | 


### PL/SQL 

**Display Passenger Information for a Flight**
| QUERY | OUTPUT |
|----|------|
| CREATE OR REPLACE PROCEDURE display_passengers_for_flight (p_flight_number IN INT) AS <br/>BEGIN <br/>FOR rec IN (SELECT * FROM Passengers WHERE Flight_Number = p_flight_number) LOOP<br/>DBMS_OUTPUT.PUT_LINE('Passenger ID: ' || rec.Passenger_ID || ', Name: ' || rec.Passenger_Name); <br/>END LOOP; <br/>END display_passengers_for_flight; | ![image](https://github.com/LuseroNajera/SQL-Projects/assets/155403528/9dd3d7c5-8977-4c59-8103-c77a46e1694b)
|



 













