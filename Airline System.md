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


| **Airplanes** | **Flight** | **Passengers** | **Flight Crew** | 
|---|---|---|---|
|CREATE TABLE Airplane ( Airplane_Number INT PRIMARY KEY); | CREATE TABLE Flight (Flight_Numbe INT PRIMARY KEY, Airplane_Number INT ); | CREATE TABLE Passengers ( Passenger_ID INT PRIMARY KEY, Passenger_Name VARCHAR2(100), Flight_Number INT,Ticket_Number INT,FOREIGN KEY (Flight_Number) REFERENCES Flight(Flight_Number)); | CREATE TABLE FlightCrew (crew_id INT PRIMARY KEY, crew_name VARCHAR(255) NOT NULL, flight_number INT NOT NULL crew_position VARCHAR(50) NOT NULL, FOREIGN KEY (flight_number) REFERENCES Flight(flight_number)); | 

### Queries

**Passenger Details with Flight Information**
| QUERY | OUTPUT |
|----|------|
|SELECT      P.Passenger_ID,       P.Passenger_Name,       P.Flight_Number,     P.Ticket_Number, F.Airplane_NumberFROM Passengers PJOIN Flight F ON P.Flight_Number = F.Flight_Number; | ![Screenshot 2024-01-18 183121](https://github.com/LuseroNajera/SQL-Projects/assets/155403528/1d969add-8ae0-499d-9c07-cc2d668a09a2) | 



**Total Passengers on Each Flight**
| QUERY | OUTPUT |
|----|------|

| SELECT
  Flight_Number,
  COUNT(*) AS total_passengers
FROM
  Passengers
GROUP BY
  Flight_Number;         | ![image](https://github.com/LuseroNajera/SQL-Projects/assets/155403528/641c979a-01e1-4f9e-994a-ebe0b7e43574) |


**Flights with Co-Pilots**
| QUERY | OUTPUT |
|----|------|

| SELECT
  P.Flight_Number,
  FC.crew_id,
  FC.crew_name,
  FC.crew_position
FROM
  Passengers P
JOIN
  FlightCrew FC ON P.Flight_Number = FC.flight_number AND FC.crew_position = 'Co-Pilot'; | ![image](https://github.com/LuseroNajera/SQL-Projects/assets/155403528/e67a91d6-f5bb-4611-a854-6e7b887ae47b) | 

  
**Counting Crew Members on each flight**
| QUERY | OUTPUT |
|----|------|

| SELECT
  F.Flight_Number,
  COUNT(CASE WHEN FC.crew_position = 'Pilot' THEN 1 END) AS num_pilots,
  COUNT(CASE WHEN FC.crew_position = 'Co-Pilot' THEN 1 END) AS num_co_pilots,
  COUNT(CASE WHEN FC.crew_position = 'Flight Attendant' THEN 1 END) AS num_flight_attendants
FROM
  Flight F
JOIN
  FlightCrew FC ON F.Flight_Number = FC.flight_number
GROUP BY
  F.Flight_Number; | ![image](https://github.com/LuseroNajera/SQL-Projects/assets/155403528/23dbf1fa-f4b5-43bc-83e6-db937eb5ffb6) | 


### PL/SQL 
| QUERY | OUTPUT |
|----|------|

