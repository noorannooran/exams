# Midterm Review
## Module 7: Using Maps and Spatial Data Types
### Bubble map
- represent quantities on maps
- size of bubble shows quantity mapped

### Color Analytical Map
- colors represent relative quantities

### Spatial Data Types
- storing definition of items from 2D geometry
	- points
	- lines
	- polygons

#### Spatial Functions
- use functions to define these items:
```
geography::STPointFromText('Point(-122.3308333 47.66063889)', 4326)
                                
//longitude								
(-122.3308333

//latitude
47.66063889)', 

//geography instance/ coordinate system to use
4326)

```

#### Polygons
- can be used to create maps

## Module 6: Charts, Images and Gauges
### Charts
- create using chart reporting item
  - bar chart
  - line
  - pie graph
- *cannot place other report items inside chart item*


#### Values
- select the items you want to display in the chart


## Module 5: Building Basic Reports
1. Run Business Intelligence Development Studio
2. Create New Project
3. Report Server Project
4. Name Project
5. Add New Data Source
6. Connect to server
7. Test Connection
<hr>
8. Add New Report
9. Add New Data Source
   - use shared data source
10. Add Dataset
11. Query Designer
	- write and test
	- **Graphical Query Designer**
	  - can add tables, join tables, select columns
	  
## Module 4 : Exploring Report Wizard
### SQL Server data tools and visual studio
- can create Integration Services packages
  - data extra
  - data transform
  - data load 
  - ETL
- can create Analysis Services BI Semantic Models

### Report Builder
- used to make reports
- make shared data set
- etc

### Module 3: Designing Accessible Data
- information is stored in tables, rows and columns
- each column has **constraints**
  - e.g. only digits, only letters, etc
- each entity has **attributes**

#### Primary Key
- each entity has a primary key
  - uniquely ID a row in the table
- Rules:
  1. every entity must have one
  2. must be unique
  
##### Composite Primary Key
- two attributes combined
  - e.g. first name + middle name + last name

### Normalization
- when there is duplicate data in several tables
- normalization is the rules = each table has attributes from only one entity

### Relation
- point at the data from another table
  - Foreign Keys
  - when the parent row is changed, the child rows will as well
- Many- to -many relationship = **linking table**
  - link two tables together in many-to-many relationship

### Retrieving Data
#### Joins
- joining two database tables

#### Inner Join
- returns information from both tables being joined
- creates a Result Set
  - denormalized data set
- includes only records that have representation on both sides

#### Outer Join
- Left Outer Join
  - not limited to values in intersection
  - includes values to the left

#### Self Join
- copy the table and join to self
  - use ALIAS to tell the two tables apart
  
### Constant and calculated fields
- NULL value can't be used in any calculation
  - must give thhis a default value
  - check if ISNULL()

### Module 2: Installing Reporting Services
#### Parts
- documentation
- Business Intelligence Project Types
  - SS Data Tools/ Visual Studio
- Report Builder
##### Windows Service
- Report Manager
- Report Server Web Service
##### SQL Server
- SQL Server Agent
- Report Server Temp DB
- Report Catalog

#### Windows Service
- responsible for two main interfaces
  - contains app that implements Report Manager website
  - provides web service interface
#### Report Server Web Service
- programmic interface for requesting reports
- interface for report server administration
- engine responsible for report rendering

#### Administration Utilities
- tools for managing Reporting Services Windows service
- making changes to the configuration
##### Reporting Services Configuration manager
- examine and modify configuration settings of Reporting Services
- can use **remote administration**

### SQL Server Database
- required to hold database for Reporting Services
  - SQL Server 2005, 2008, 2008 R2, 2012
- uses SQL Server agent
- **databases in SQL Server can be used as data sources**

### SQL Server Agent
- part of the installation
- executes jobs scheduled to run
  - e.g. back up database
  - transfer information
  
### Two Databases:
#### Report Server DB
- Report Catalog
- info about report structure
#### Report Server Temp DB	
- temp storage
- **execution cache**
  - recently executed reports


### Installation Types
#### Distributed Installation
- installation split between two computers
- one runs SQL Server and the Report Catalog Databases
- the other runs Reporting Services Windows service (Report Server)
##### PROS
- scalability
- can handle more users
##### CONS
- complex to install and administer

#### Scale-Out
- specialized form of distributed installation
- single dtaabase server interacts with several report servers
- can handle more simultaneous users
- reports can be deployed to any report server and end up in same database

#### SharePoint Integrated Mode Installation
- sharepoint server provides the interfaces
- reports are stored as documents
  - can manage like excel or word documents
  - searching and version control
- sharepoint security can be applied

## Module 1 : Intro to Report Design
### Reporting services
- uses dynamic html
- don't need to know how to program
- any browser that supports html 4.0 can view reports
- can use with printers
- free with SQL Server 2012 License

#### Creating reports
- Report Builder
- Report Designer < SQL Server Data Tools / Visual Studio

### Report Structure
#### Data Definition
- controls where the data will come from and what will be selected from the data
  1. Data Source
	 - data file or db server that provides information
  2. Data Set
#### Report layout
- controls how the information will be presented

#### Design Surface
- where you create report layout using:
  1. Report Data Windows
  - Toolbox
  - Properties
  
## Midterm Review: Practice Q&A

15. What is a shared Data Source?
> A data source that is shared between all reprts in a report project

14. What is a Drilldown in SSRS Reports?
> Interactive feature visualizing groups

13. Which one is a matrix?
> A table with changing rows and changing columns

12. What does a Data Source in SSRS consist of?
> a. Connection String
> b. Source Server Name
> c. Log on Method to the server
> d. All of the above **

11. Which type of join between two tables might have more number of records in its results?
> a. Outer Join

10. What cardinality of relationship is possible between tables in SQL server (directly or indirectly)?
> d. All of the above:
> a. One-to-One
> b. Many-to-One
> c. Many-to-Many

9. Which one is a **must** feature for the Server Installation of SSRS?
> b. Report Server Web Service

8. Which SQL Server 2012 Edition does **not** include SSRS?
> b. Express Edition

7. Which Requirement can be fulfilled using SSRS complete installation?
> d. All of the above:
> a. Email and schedule reports
> b. View reports in HTML format
> c. View reports in PDF format

6. Which is **not** a part of Report Server (assuming complete insyallation)?
> a. Data Sources

5. What system can be used for the data source of a report?
> d. Any system with a data provider can be used

4. WHat can you create in the data region of an SSRS report?
> d. All of the above:
> a. chart
> b. Tablix
> c. Image

3. What is a data set in SSRS report?
> d. Both A & B
> a. A query
> b. the meta data of a query

2. What is an RDL File?
> d. An XML file with the defintion of a complete report

1. Which is **not** a part of SSRS Report Authoring Architecture?
> c. Microsoft Word 2012
> Report Builder and Report Designer are both parts of SSRS
