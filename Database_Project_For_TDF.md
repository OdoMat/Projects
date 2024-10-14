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

  **create database TourDeFranceDB;**
  
  **create table Cycling_Teams (  
    TeamID INT auto_increment primary key,  
    TeamName varchar(500),  
    Location varchar(50)  
    );**

  **create table Cyclists (  
    CyclistID INT auto_increment primary key,  
    FirstName varchar(50),  
    LastName varchar(50),  
    Birthdate date,  
    TeamID INT,   
    foreign key (TeamID) references Cycling_Teams(TeamID)  
    );**



  After the database and the tables have been created, a few ALTER instructions were written in order to update the structure of the database, as described below:

**Inserati aici toate instructiunile de ALTER pe care le-ati scris. Incercati sa includeti instructiuni cat mai variate cum ar fi:**
 **- schimbare nume tabela**
 **- adaugare sau stergere coloana**
 **- redenumire coloana**
 **- adaugare proprietati coloana (ex: adaugare auto-increment)**
 **- modificare proprietati coloana (ex: modificare tip de data, modificare pozitie coloana etc)**
 **- adaugare cheie primara sau secundara (daca nu a fost deja adaugata la crearea tabelei)**
 
  
### DML (Data Manipulation Language)

  In order to be able to use the database I populated the tables with various data necessary in order to perform queries and manipulate the data. 
  In the testing process, this necessary data is identified in the Test Design phase and created in the Test Implementation phase. 

  Below you can find all the insert instructions that were created in the scope of this project:

  **Inserati aici toate instructiunile de INSERT pe care le-ati scris. Incercati sa folositi atat insert pe toate coloanele (fara sa precizati pe ce coloane se face insert) cat si insert pe cateva coloane (care necesita mentionarea explicita a coloanelor pe care se face insert). De asemenea, incercati sa acoperiti situatia in care inserati mai multe randuri in acelasi timp**

  After the insert, in order to prepare the data to be better suited for the testing process, I updated some data in the following way:

  **Inserati aici toate instructiunile de UPDATE pe care le-ati scris folosind filtrarile necesare astfel incat sa actualizati doar datele de care aveti nevoie**

After the testing process, I deleted the data that was no longer relevant in order to preserve the database clean: 

**Inserati aici toate instructiunile de DELETE pe care le-ati scris folosind filtrarile necesare astfel incat sa stergeti doar datele de care aveti nevoie**


### DQL (Data Query Language)


In order to simulate various scenarios that might happen in real life I created the following queries that would cover multiple potential real-life situations:

**Inserati aici toate instructiunile de SELECT pe care le-ati scris folosind filtrarile necesare astfel incat sa extrageti doar datele de care aveti nevoie**
**Incercati sa acoperiti urmatoarele:**<br>
**- where**<br>
**- AND**<br>
**- OR**<br>
**- NOT**<br>
**- like**<br>
**- inner join**<br>
**- left join**<br>
**- OPTIONAL: right join**<br>
**- OPTIONAL: cross join**<br>
**- functii agregate**<br>
**- group by**<br>
**- having**<br>
**- OPTIONAL DAR RECOMANDAT: Subqueries - nu au fost in scopul cursului. Puteti sa consultati tutorialul [asta](https://www.techonthenet.com/mysql/subqueries.php) si daca nu intelegeti ceva contactati fie trainerul, fie coordonatorul de grupa**<br>

## Conclusions

Inserati aici o concluzie cu privire la ceea ce ati lucrat, gen lucrurile pe care le-ati invatat, lessons learned, un rezumat asupra a ceea ce ati facut si orice alta informatie care vi se pare relevanta pentru o concluzie finala asupra a ceea ce ati lucrat


