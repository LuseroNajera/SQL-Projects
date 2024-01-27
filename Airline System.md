# **Arline System** <img src="https://github.com/LuseroNajera/SQL-Projects/assets/155403528/5b94e831-01f9-41f1-ad16-9ee461b8b6c8" width="50" height="50">

***

### Table of Contents
- [Purpose](#Purpose)
- [ERD](#ERD) 
- [Tables](#Tables)
- [Queries](#Queries)
- [PL/SQL](#PL/SQL) 

***

### Purpose
The simple airline system aims to store and manage data related to flights, passengers, airplanes, and flight crew members.

***

### ERD 
Entity Relationship Diagram
* This diagram provides a visual representation of the data structure within an airline system. With this, I have defined the tables, fields, and relationships that will be implemented in the database schema. This ERD can serve as a sort of document that can aid in future modifications and troubleshooting. 

* ![image](https://github.com/LuseroNajera/SQL-Projects/assets/155403528/5f1fb243-2835-4e4e-847b-f68a6960f69e)

***

### Tables 

| **Airplanes** | **Flight** | **Passengers** | **Flight Crew** | 
|---|---|---|---|
|CREATE TABLE Airplane ( Airplane_Number INT PRIMARY KEY); | CREATE TABLE Flight (Flight_Numbe INT PRIMARY KEY, Airplane_Number INT ); | CREATE TABLE Passengers ( Passenger_ID INT PRIMARY KEY, Passenger_Name VARCHAR2(100), Flight_Number INT,Ticket_Number INT,FOREIGN KEY (Flight_Number) REFERENCES Flight(Flight_Number)); | CREATE TABLE FlightCrew (crew_id INT PRIMARY KEY, crew_name VARCHAR(255) NOT NULL, flight_number INT NOT NULL crew_position VARCHAR(50) NOT NULL, FOREIGN KEY (flight_number) REFERENCES Flight(flight_number)); | 

***

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

*** 

### PL/SQL 

**Display Passenger Information for a Flight**

* This procedure will take a Flight_Number as input and then displays detailed information for each passenger on that flight.

| QUERY | OUTPUT |
|----|------|
| CREATE OR REPLACE PROCEDURE display_passengers_for_flight (p_flight_number IN INT) AS <br/>BEGIN <br/>FOR rec IN (SELECT * FROM Passengers WHERE Flight_Number = p_flight_number) LOOP<br/>DBMS_OUTPUT.PUT_LINE('Passenger ID: ' \\ rec.Passenger_ID \\ ', Name: ' \\ rec.Passenger_Name); <br/>END LOOP; <br/>END display_passengers_for_flight; | ![image](https://github.com/LuseroNajera/SQL-Projects/assets/155403528/9dd3d7c5-8977-4c59-8103-c77a46e1694b)  |

**Display Specific Flight Passengers and Details**

* This procedure will take a Flight_Number as input, and then calculate the total number of passengers for that flight, as well as display the flight details.

| QUERY | OUTPUT |
|----|------|
| CREATE OR REPLACE PROCEDURE calculate_flight_passengers (p_flight_number IN INT) AS<br/>v_total_passengers INT;<br/>BEGIN<br/>SELECT COUNT(*) INTO v_total_passengers<br/>FROM Passengers <br/>WHERE Flight_Number = p_flight_number;<br/>DBMS_OUTPUT.PUT_LINE('Flight Details for Flight ' \\ p_flight_number \\ ':');<br/>FOR rec IN (SELECT * FROM Flight WHERE Flight_Number = p_flight_number) LOOP <br/>DBMS_OUTPUT.PUT_LINE('Airplane Number: ' \\ rec.Airplane_Number); <br/>END LOOP; <br/>DBMS_OUTPUT.PUT_LINE('Total Passengers: ' \\ v_total_passengers); <br/>END calculate_flight_passengers; | ![image](https://github.com/LuseroNajera/SQL-Projects/assets/155403528/6f74e7cf-d7b4-47aa-a4a4-fbd347a54ed3) |
 













