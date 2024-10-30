# Database Project for Tour de France

The scope of this project is to use all the SQL knowledge gained throught the Software Testing course and apply them in practice.

**Application under test:** Tour de France

**Tools used:** MySQL Workbench

**Database description:** The Tour de Franca Database is designed to manage information about cycling teams, cyclists, race stages, race result and rankings troughout the competition.

## Database Schema 
  
You can find below the database schema that was generated through Reverse Engineer and which contains all the tables and the relationships between them.

![Reverse engineer](https://github.com/user-attachments/assets/be3924f4-a78d-4827-8c9f-fdc46ad016cf)


The tables are connected in the following way:

- **Teams**  is connected with **Cyclists** through a **one to many** relationship which was implemented through **Teams.TeamID_primary_key** as a primary key and **Cyclists.TeamID_foreign_key** as a foreign key
- **Cyclists**  is connected with **RaceResults** through a **one to many** relationship which was implemented through **Cyclists.CyclistID_primary_key** as a primary key and **RaceResults.CyclistID_foreign_key** as a foreign key
- **Stages**  is connected with **RaceResults** through a **one to many** relationship which was implemented through **Races.StageID_primary_key** as a primary key and **RaceResults.StageID_foreign_key** as a foreign key
- **Cyclists**  is connected with **Rankings** through a **one to one** relationship which was implemented through **Cyclists.CyclistID_primary_key** as a primary key and **Rankings.CyclistID_foreign_key** as a foreign key

## Database Queries

### DDL (Data Definition Language)

  The following instructions were written in the scope of CREATING the structure of the database (CREATE INSTRUCTIONS)
```
  create database TourDeFranceDB;
```
```  
  create table Cycling_Teams (  
    TeamID INT auto_increment primary key,  
    TeamName varchar(500),  
    Location varchar(50)  
    );
```
```
  create table Cyclists (  
    CyclistID INT auto_increment primary key,  
    FirstName varchar(50),  
    LastName varchar(50),  
    Birthdate date,  
    TeamID INT,   
    foreign key (TeamID) references Cycling_Teams(TeamID)  
    );
```
```
  create table Stages (  
  StageID INT auto_increment primary key,  
  StageName varchar(100),  
  Distance decimal(5,2),  
  StageDate date  
  );
```
```
  create table RaceResults (  
  ResultID INT auto_increment primary key,  
  CyclistID INT,  
  StageID INT,  
  Position INT,                                                    
  Points INT,                                                       
  foreign key (CyclistID) references Cyclists(CyclistID),  
  foreign key (StageID) references Stages(StageID)  
  );
```
```
  create table Rankings (  
  RankingID INT auto_increment primary key,  
  CyclistID INT,  
  Distance decimal (5,2),  
  GeneralTime time  
  );
```
  After the database and the tables have been created, a few ALTER instructions were written in order to update the structure of the database, as described below:
```
 drop table Rankings; -- delete the Rankings table   
```
```
 alter table Cycling_Teams rename to Teams; -- Changing the name of the table Cycling_Teans into Teams
```
```
 alter table Teams modify TeamName varchar(100); -- Chanching the proprities of the TeamName column from varchar(500) intro varchar(100)
```
```
 alter table Teams change Location Country varchar(50); -- Changing the name of the column Location into Country
```
```
 alter table Cyclists add column Nationality varchar(50); -- Adding the column Nationality into the Cyclists table
```
```
 alter table Cyclists modify Nationality varchar(50) after Birthdate; -- Changing the position of the column Nationality
```
```  
 alter table Cyclists modify Nationality varchar(50) after Birthdate; -- Changing the position of the column Nationality
```
```
 alter table Stages add column TimeTaken time; -- Adding a new column named TimeTaken to the Stages table
```
```
 alter table RaceResults add column TimeTaken time; -- Adding a new column named TimeTaken to the RaceResults Table
```
```
 alter table RaceResults modify TimeTaken time after Position; -- Changing the position of the TimeTaken column
```
```
 alter table RaceResults change Points PointsEarned INT -- Chancing the name of the column from Points into PointsEanred  
 ``` 
### DML (Data Manipulation Language)

  In order to be able to use the database I populated the tables with various data necessary in order to perform queries and manipulate the data. 
  In the testing process, this necessary data is identified in the Test Design phase and created in the Test Implementation phase. 

  Below you can find all the insert instructions that were created in the scope of this project:
```
  INSERT INTO Teams (TeamName, Country)  
  VALUES ('UAE TEAM EMIRATES ', 'UAE'),  
  ('JUMBO-VISMA', 'Netherlands'),  
  ('INEOS  GRENADIERS', 'United Kingdom'),  
  ('MOVISTAR', 'Spain'),  
  ('LIDL-TREK', 'USA');
```
```
  INSERT INTO Cyclists (FirstName, LastName, Birthdate, Nationality, TeamID)  
  VALUES ('Tadej', 'Pogacar', '1998-09-21', 'Slovenian', 1),  
  ('Adam Yates', 'Bernal', '1992-08-07', 'British', 1),  
  ('Jonas', 'Vingegaard', '1997-02-10', 'Danish', 2),  
  ('Wout', 'Van Aert', '1994-09-15', 'Belgian', 2),  
  ('Geraint', 'Thomas', '1986-05-25', 'British', 3),  
  ('Tom', 'Pidcock', '1999-07-30', 'British', 3),  
  ('Nairo', 'Quintana', '1990-02-04', 'Colombian', 4),  
  ('Enric', 'Mass', '1986-01-07', 'Spanish', 4),  
  ('Giulio', 'Ciccone', '1994-12-20', 'Italian', 5),  
  ('Julien', 'Bernard', '1992-03-17', 'French', 5);
```
```
  INSERT INTO Stages (StageName, Distance, StageDate)  
  VALUES ('Stage 1 - Nice to Sisteron', 198.0, '2024-07-01'),  
  ('Stage 3 - Sisteron to Orcières', 199.2, '2024-07-02'),  
  ('Stage 4 - Gap to Privas', 183.4, '2024-07-03'),  
  ('Stage 4 - Macon to Dijon', 163.5, '2024-07-04'),  
  ('Stage 5 - Agen to Pau', 211.0, '2024-07-05');
```
```
  INSERT INTO RaceResults (CyclistID, StageID, Position, TimeTaken, PointsEarned)  
  VALUES (1, 1, 1, '05:10:30', 90),  -- Tadej Pogacar wins Stage 1  
  (3, 1, 2, '05:11:00', 80),  -- Jonas Vingegaard takes second place in Stage 1  
  (4, 1, 3, '05:12:15', 70),  -- Wout Van Aert takes third place in Stage 1  
  (5, 1, 4, '05:13:20', 60),  -- Geraint Thomas takes fourth place in Stage 1  
  (2, 1, 5, '05:14:45', 50),  -- Adam Yates takes fifth place in Stage 1  
  (6, 1, 6, '05:15:25', 40),  -- Tom Pidcock takes sixth place in Stage 1  
  (10, 1, 7, '05:15:40',30),  -- Julien Bernard takes seventh place in Stage 1  
  (7, 1, 8, '05:16:20', 20),  -- Nairo Quintana takes eighth place in Stage 1  
  (9, 1, 9, '05:17:45', 10),  -- Giulio Ciccone takes ninth place in Stage 1  
  (8, 1, 10, '05:18:00', 0);  -- Enric Mass takes tenth place in Stage 1
```
```
  INSERT INTO RaceResults (CyclistID, StageID, Position, TimeTaken, PointsEarned)  
  VALUES (3, 2, 1, '04:30:45', 90),  -- Jonas Vingegaard wins Stage 2  
  (1, 2, 2, '04:30:55', 80),  -- Tadej Pogacar takes second place in Stage 2  
  (4, 2, 3, '04:40:15', 70),  -- Wout Van Aert takes third place in Stage 2  
  (2, 2, 4, '04:40:20', 60),  -- Adam Yates takes fourth place in Stage 2  
  (5, 2, 5, '04:40:35', 50),  -- Geraint Thomas takes fifth place in Stage 2  
  (6, 2, 6, '04:40:40', 40),  -- Tom Pidcock takes sixth place in Stage 2  
  (10, 2, 7, '04:42:30', 30),  -- Julien Bernard takes seventh place in Stage 2  
  (8, 2, 8, '04:43:05', 20),  -- Enric Mass takes eighth place in Stage 2  
  (9, 2, 9, '04:45:50', 10),  -- Giulio Ciccone takes ninth place in Stage 2  
  (7, 2, 10, '04:55:20', 0);  -- Nairo Quintana  takes tenth place in Stage 2
```
```
  INSERT INTO RaceResults (CyclistID, StageID, Position, TimeTaken, PointsEarned)  
  VALUES (1, 3, 1, '05:18:45', 90),  -- Tadej Pogacar wins Stage 3  
  (3, 3, 2, '05:23:55', 80),  -- Jonas Vingegaard takes second place in Stage 3  
  (6, 3, 3, '05:24:15', 70),  -- Tom Pidcock takes third place in Stage 3  
  (4, 3, 4, '05:25:27', 60),  -- Wout Van Aert takes fourth place in Stage 3  
  (7, 3, 5, '05:25:37', 50),  -- Nairo Quintana takes fifth place in Stage 3  
  (2, 3, 6, '05:35:40', 40),  -- Adam Yates takes sixth place in Stage 3  
  (5, 3, 7, '05:35:55', 30),  -- Geraint Thomas takes seventh place in Stage 3  
  (10, 3, 8, '05:40:15', 20),  -- Julien Bernard takes eighth place in Stage 3  
  (8, 3, 9, '05:40:30', 10),  -- Enric Mass takes ninth place in Stage 3  
  (9, 3, 10, '05:41:20', 0);  -- Giulio Ciccone takes tenth place in Stage 3
```
```
  INSERT INTO RaceResults (CyclistID, StageID, Position, TimeTaken, PointsEarned)  
  VALUES (3, 4, 1, '04:30:45', 90),  -- Jonas Vingegaard wins Stage 4  
  (1, 4, 2, '04:30:55', 80),  -- Tadej Pogacar takes second place in Stage 4  
  (4, 4, 3, '04:40:15', 70),  -- Wout Van Aert takes third place in Stage 4  
  (2, 4, 4, '04:40:20', 60),  -- Adam Yates takes fourth place in Stage 4  
  (5, 4, 5, '04:40:35', 50),  -- Geraint Thomas takes fifth place in Stage 4  
  (6, 4, 6, '04:40:40', 40),  -- Tom Pidcock takes sixth place in Stage 4  
  (10, 4, 7, '04:42:30', 30),  -- Julien Bernard takes seventh place in Stage 4  
  (8, 4, 8, '04:43:05', 20),  -- Enric Mass takes eighth place in Stage 4  
  (9, 4, 9, '04:45:50', 10),  -- Giulio Ciccone takes ninth place in Stage 4  
  (7, 4, 10, '04:55:20', 0);  -- Nairo Quintana  takes tenth place in Stage 4
```
```
  INSERT INTO RaceResults (CyclistID, StageID, Position, TimeTaken, PointsEarned)  
  VALUES (1, 1, 1, '05:05:30', 90),  -- Tadej Pogacar wins Stage 5  
  (3, 1, 2, '05:06:00', 80),  -- Jonas Vingegaard takes second place in Stage 5  
  (4, 1, 3, '05:06:15', 70),  -- Wout Van Aert takes third place in Stage 5  
  (5, 1, 4, '05:06:20', 60),  -- Geraint Thomas takes fourth place in Stage 5  
  (2, 1, 5, '05:10:45', 50),  -- Adam Yates takes fifth place in Stage 5  
  (6, 1, 6, '05:11:25', 40),  -- Tom Pidcock takes sixth place in Stage 5  
  (10, 1, 7, '05:11:40', 30),  -- Julien Bernard takes seventh place in Stage 5  
  (7, 1, 8, '05:15:20', 20),  -- Nairo Quintana takes eighth place in Stage 5  
  (9, 1, 9, '05:15:45', 10),  -- Giulio Ciccone takes ninth place in Stage 5  
  (8, 1, 10, '05:15:55', 0);  -- Enric Mass takes tenth place in Stage 5
```
 
  After the insert, in order to prepare the data to be better suited for the testing process, I updated some data in the following way:
```
  UPDATE Stages  
  SET StageName = 'Stage 2 - Sisteron to Orcières'  
  WHERE StageName = 'Stage 3 - Sisteron to Orcières' AND StageDate = '2024-07-02';
```
```
  UPDATE Stages  
  SET StageName = 'Stage 3 - Gap to Privas'  
  WHERE StageName = 'Stage 4 - Gap to Privas' AND StageDate = '2024-07-03';
```  
```
  UPDATE RaceResults  
  SET StageID = 5  
  WHERE StageID = 1  
  AND TimeTaken IN ('05:05:30', '05:06:00', '05:06:15', '05:06:20', '05:10:45', '05:11:25', '05:11:40', '05:15:20', '05:15:45', '05:15:55');
```

After the testing process, I deleted the data that was no longer relevant in order to preserve the database clean: 
```
alter table Stages drop column TimeTaken;** -- Deleting the TimeTaken column from the Stages table
```

### DQL (Data Query Language)

In order to simulate various scenarios that might happen in real life I created the following queries that would cover multiple potential real-life situations:
```
  SELECT FirstName, LastName, Nationality  
  FROM Cyclists  
  WHERE Nationality = 'British'; -- Retrieve all cyclists from UK<br>
```
```
  SELECT FirstName, LastName, Nationality  
  FROM Cyclists  
  WHERE Nationality = 'British' OR Nationality = 'Colombian'; -- Get all cyclists who are from either "UK" or "Colombia<br>
```
```
  SELECT FirstName, LastName, Nationality, TeamID  
  FROM Cyclists  
  WHERE Nationality = 'British' AND TeamID = 1; - Get all British cyclists who are on "Team UAE" <br>
```
```
  SELECT FirstName, LastName, Nationality  
  FROM Cyclists  
  WHERE NOT Nationality = 'British'; -- Get all cyclists who are not from the "UK." <br>
```
```
  SELECT FirstName, LastName  
  FROM Cyclists  
  WHERE FirstName LIKE 'T%'; -- Find all cyclists whose first name starts with the letter "T"<br>
```
```
  SELECT c.FirstName, c.LastName, t.TeamName  
  FROM Cyclists c  
  INNER JOIN Teams t ON c.TeamID = t.TeamID; -- List all cyclists along with their team names.<br>
```
```
  SELECT c.FirstName, c.LastName, s.StageName  
  FROM Cyclists c  
  CROSS JOIN Stages s; -- Combine all cyclists with all stages<br>
```
```
  SELECT c.FirstName, c.LastName, r.Position  
  FROM Cyclists c  
  LEFT JOIN RaceResults r ON c.CyclistID = r.CyclistID; --  List all cyclists and their race results, showing cyclists who haven't participated in a race<br>
```  
```
  SELECT COUNT(CyclistID) AS TotalCyclists  
  FROM Cyclists; -- Find the total number of cyclists.<br>
```
```
  SELECT SUM(Distance) AS TotalDistance  
  FROM Stages; -- Find the total distance from all stages.<br>
```
```
  SELECT AVG(PointsEarned) AS AvgPoints  
  FROM RaceResults  
  WHERE StageID = 1; -- Find the average points earned by cyclists in Stage 1.<br>
```
```
  SELECT c.FirstName, c.LastName, SUM(r.PointsEarned) AS TotalPoints  
  FROM Cyclists c  
  INNER JOIN RaceResults r ON c.CyclistID = r.CyclistID  
  GROUP BY c.CyclistID; -- Get the total points earned by each cyclist.<br>
```
```
  SELECT c.FirstName, c.LastName, SUM(r.PointsEarned) AS TotalPoints  
  FROM Cyclists c  
  INNER JOIN RaceResults r ON c.CyclistID = r.CyclistID  
  GROUP BY c.CyclistID  
  HAVING TotalPoints > 200; -- Get cyclists who have earned more than 200 points.<br>
```
```
  SELECT FirstName, LastName   
  FROM Cyclists  
  WHERE CyclistID IN (  
  SELECT CyclistID   
  FROM RaceResults   
  WHERE Position = 1);  -- Get all cyclists who have won a stage.<br>  
```
## Conclusions

Throughout this project, using the virtual Tour de France database, I gained hands-on experience with a range of SQL techniques essential for working with relational databases.This excercise helped me understand how joins connect data between tables, how aggregate functions can reveal useful patterns and summaries, and how to efficently extract, filter and manipulate data. This skills will be valuable for managing databases, analyzing data and creating reports in future projects.


