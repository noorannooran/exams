# Final Exam Review
- Modules 8, 9, 10, 11 and 12
- (Report-Authoring Practices slides 25-33).

<hr>

# Module 8


<hr>

# Module 9
## Advanced Reports
- adding .NET code to report items

### IIF
- e.g. BorderStyle
```
=IIF(Fields!StatusName.Value ="Lost", "None, "Solid")
```

### Calculated Column
- can be added to tablix

### Totals
- can add totals
<hr>

# Module 10
## Managing Report Execution
### Folders
- in the report catalog, reports are arranged in Folders
- can contain:
	- reports
	- supporting files (external images and shared data sources)
	- other folders
- cannot find these folders on the File System
- they are screen representations  of records in the Report Catalog

#### Report Folder names
- cannot include special characters:
	> //;  //: //@ //& //= //+ //$ //, //\ //* //< //> //| //" /
- cannot consist of dots or spaces
- can be assigned a description
	- both name and description are searchable

### Report Manager
- web application:
	- provides a straightforward method of navigating Report Catalog
	- **Home** folder is created by default
	- default URL: **http://ComputerName/reports**
		- or https: if using secure connection
	- if on the same computer where Report Services is running:
		- **http://localhost/reports**
- Hide in tile view
	- when this is checked, new folders do not appear in Home folder

#### Deploying Reports Using Report Designer
- most common method of moving reports to report server
- Select properties of project:
- type TargetDataSourceFolder
	- where report will be deployed
- type TargetReportFolder
	- where report will be deployed
- type serverURL for TargetServerURL
	

### Working through the web Service
- when Report Designer deploys reports, works through the Reporting Services web service
- interface for other programs to communicate with Reporting Services
- **Web Service URL** is different from REport Manager:
	- Default URL **http://ComputerName/ReportServer**

### Deploying a Single Project
- right click a report and select Deploy
	- this will only deploy the selected report
- whenever a report is deployed, shared data sources are automatically deployed with it
- if OverwriteDataSources is set to True
	- data source from development environment will overwrite the production environment
	- to avoid this, set OverwriteDataSources to false

### Uploading Reports Using Report Manager
- pulling the reports from the development environment to the report server
- report author can place RDL Report Definition Language file in a shared directory
- report can be uploaded to the production server after testing

### Hiding Items
- you don't want there to be clutter when users are looking for reports
- can Hide in Tile View
- can view using Detail View or other Views

#### Connect Using Options
- need some type of credentials to data
- do not include credentials in the connection string to the data source
	- connection string is stored as plaintext
##### Options:
1. Credentials Supplied By User
	- user must log in with a username and password each time the report is run
	- Use as Windows Credentials:
		- treated as a Windows Login
	- not checked:
		- treated as a database login
2. Credentials Stored in the Report Server
	- username and password stored in the Report Catalog
	- encrypted when stored in the catalog
	- not displayed to the user
	- convenient to the user because they don't need to re-enter credentials
3. Integrated Security
	- when not comfortable storing credentials in report catalog
	- also do not want users entering credentails every time
	- does not require user to enter credentials
	- takes Windows login credentials and passes them to database server
4. Credentials Not Required
	- for data sources that do not require authentication
	- connection to some Access databases, FoxPro databases
	- could be used if you put credentials in connection string
	- not secure at all

### Modifying Reports from the Report Server
- can download a report definition, modify and send back to the report server as an update
- if you already have the RDL file for a report, you can edit that report and re-deploy it

### Exporting Types
- presentation rendering formats:
	- retain layout, font, color, graphics
	- Preview
	- HTML
	- TIFF image
	- Adobe PDF
	- MHTML (web archive)
	- Excel
	- Word
	- Print

#### Groups
1. Interactive Presentation Rendering Formats
	- support interactive features of reports
	- Preview
	- HTML
2. Physical Page presentation formwats
	- concerned with fitting content on page size
	- TIFF image
	- Adobe PDF
	- print
3. Logical page presentation formats
	- concerned with formatting for viewing on a screen
	- MHTML
	- Excel
	- Word
4. Data Exchange Rendering Formats
	- contain data portion of report, with minimal formatting
	- for use with other computer programs
	- CSV (comma separated values)
	- XML (extensible markup language)

### Managing Reports on Report Server
1. Security
	- reports contain sensitive data
	- must only be accessed by appropriate people
2. Performance
	- return information in a reasonable amount of time
	- least stress on database resources

### Security
- Flexibility:	
	- individual access rights can be assigned to each folder
	- and each item within a folder
- Security Inheritance, security roles, integration with Windows Security

#### Integration With Windows Security
- does not maintain own list of users and passwords
- user must have valid domain user name and password 
- or user must have valid local username and password to log on to report server
- user can only acccess folders and itmes that have rights to in the Report Manager

#### Tasks and Rights
| Task | Description |
|------|-------------|
| Consume reports | Read report definitions |
| Create Linked reports | create linked reports and publish to a report server folder |
| Manage all subscriptions | view, modify, delete subscription regardless of who owns it |
| Manage data sources | create and delete shared data sources, modify properties|
| Manage folders | Create, view, delete folders, modify properties |
| Manage individual subscriptions| create, view, modify, delete subscriptions they own |
| Manage models | create, view, delete models; view and modify properties |
| Manage report history | create, view, detele report history snapshots; modify properties |
| Manage reports | create, delete reports; modify report properties |
| Manage resources | create, modify, delete resources; modify properties |
| Set security for individual items | View, modify security settings for reports, folders, resources, shared data sources |
| View Data sources | View shared data source items in folder hierarchy ; view properties |
| View folders | View folder items in the hierarchy, view folder properties |
| View Models | View models in the hierarchy, use models as data source sfor a report, run queries against the model to retrieve data |
| View Reports | view reports and linked reports in hierarchy; view report history snapshots and report properties |
| View Resources | view resources in folder hierarchy ; view resource properties |

#### System Tasks with associated Rights
| Task | Defintion|
|------|----------|
| Execute report definitions | start execution from report defintion without publishing it to the report server |
| Generate events | provides application with ability to generate events within the report server namespace |
| Manage jobs | View and cancel running jobs |
| Manage report server properties | Vieww and modify properties that apply to the report server and to items managed by the report server |
| Manage roles | Create, view, modify, delete role defintions |
| Manage shared schedules | Create, view, modify, delete shared shcedules used to run reports |
| View Report server properties | view properties that apply to the report server |
| View shared schedules | view predefined schedule that has been made available to general use |

### Roles
- rights to perform tasks are grouped together to create roles

#### Browser Role
- basic role: view reports, not create folders or upload new reports
- Manage individual subscriptions
- View folders
- View Models
- View Reports
- View Resources

#### Publisher Role
- create folders and upload reports
- Create Linked Reports
- Manage data sources
- Manage folders
- Manage Models
- Manage reports
- Manage resources

#### MY reports Role
- only with special folder called My Reports folder
- gives rights to do everything except change security settings
- Create Linked reports
- Manage data sources
- Manage folders
- Manage individual subscriptions
- Manage report history
- Manage reports
- Manage resources
- View data soruces
- view folders
- view reports
- view resources

#### The Content Manager Role
- for users who are managing folders, reports, resurces
- all members of Windows Local administrators group are automatically members of Content Manager role for all folders, reports, resources
- rights to perform all tasks including system-wide tasks

#### THe Report Builder Role
- gives users right to create and edit reports
- Consume Reports
- Manage Individual Subscriptions
- View Folders
- View models
- View Report Definitions
- View reports
- View resources
 
#### The System USer Role
- system wide security tasks
- Execute report defintions
- view report server properties
- view shared schedules

#### System Administrator Role
- provides user with rights to complete any tasks necessary to manage the report server
- all memeber of Windows local Administrators group are automatically member of this group
- Execute report definitions
- manage jobs
- manage report server properties
- manage report server security
- manage roles
- manage shared schedules


<hr>

## Module 11
### Report Parts
- similar to shared datasets
- have a report layout component
- created by taking layout components and params of an existing report and saving to the report server
- can be incorporated into other reports
- **only** Report Builder can use report parts

#### To publish report parts
- select Publish Report Parts
	- check the boxes next to items and params you want to save
	- press OK

### Caches
- data is re-queried each time the report is executed
- if the same param values are chosen, the report server pulls the informatin from the cache

#### Cached Report Expiration
- a cached report is assigned an expiration date and time
- can be calculated by X minutes after existing
	- good for: report that requires a large amount of database resources
	- is run often
	- does not need updated data
- can be calculated by scheduling a date and time to be deleted
	- good for: reports that change on a scheduled basis

#### Creating a Cached Report
- report must be stored using credentials	
	- ie. Windows logon or database logon
	- stored with the data source

### Report Snapshots
- a way to create a cached report instance
- on a scheduled basis, or when a feature is turned n

### Report History
- keep copies of a report's past execution
- save state of data without saving the data itself
- can use for trend analysis or verifying information

#### Report History Snapshots and Report Parameters
- default value required for parameters
- parameters can't change when each snapshot is created
- in order to do this for other parameter values,
	- linked reports with params defaulted to the other values

#### Setting Limits on the number of report history snapshots
- set a limit using the Snapshot Options

#### Report History Snapshots
- they are not lost if you change the original report

### Subscriptions
- **push** technology scenario
- Reporting services initiates the execution of the report and sends the report to the user
- By Going to the report, Selecting Manage > Subscriptions, adding e-mails
- it is possible to have multiple subscriptions to one report
	- e.g. one monthly, one weekly
	- OR receive report run for multiple sets of parameters
		- you can specify param values for subscription properties

#### Embedded VS Attached Report
- a report can show up as embedded in an HTML email
	- Web Archive Format
- or as an attached document
	- any other formats
	- use PDF if unsure of user's email client capabilities

### Security
- to subscribe to a report or create a subscription you must have rights to Manage Individual Subscriptions:
- roles that can manage individual subscriptions:
	- the Browser
	- Content Manager
	- My Reports

### Data-Driven Subscription
- make a report and e-mail it to people on a mailinglist
- queried from Reporting Services data source

#### General site settings
- set several values and configuration options 

<hr>

## Module 12 
### Report Authoring Practices
1. Use Report Templates
	- for company logos
	- for page numbers and dates
	- will provide consistent look to your reports
2. Use Shared Data Sources
	- centralize the storage of database credentials
	- fewer places exist to change connection information
	- if logon credentials are changed, same thing: fewer changes to make
	- production and development database servers
	- shared datasource that points to the development database server
	- shared datasource can also point to production database server
	- **Overwrite Data Sources** option turned **off**:
		- data source from development doesn't overwrite the one for production

### Report Deployment Practices
1. Create a backup of the encryption key
	- helps protect all reports and shared data sources
	- if the original key becomes corrupt, the config file can't be decrypted
		- use a backup
2. Review Reports Before Deploying
	- before putting into production
	- make sure efficient queries are beng used
	- make sure the information claimed is the information from the database
3. Use Linked Reports
	- instead of deploying duplicate copies
	- each linked report can have own default params and own security
	- updates to the report are done in centralized location
	- prevent confusion from multiple versions of a report
4. Use Folders and Descriptions to Organize Reports
	- logical groupings
	- use tree structure to create multi-level structures
	- enough folders for organization, but not too much
	- meaningful report names
	- meaningful descriptions
		- searchable in Report Manager
5. Assign Security at the Folder Level
	- let reports inherit security from the folders they reside in
6. Assign Security to Domain groups
	- rather than to individual user
		- too complex
	- simple is better
7. Assign Only the Rights needed
	- no security breaches
	- custom security roles
		- use with the domain groups
8. Hide Items
	- keep folders looking clean
	- hide items users do not need
		- e.g. shared data sources
		- subreports
	- **Hide in Tile View**
9. Deploy Supporting Items to the Report Server
	- documentation for reports:
		- Word Docs
		- pdfs
		- Excel spreadsheets
		- ppt
	- can be deployed to the server
10. Use Caching and Snapshots
	- reduct load on the report server and increase performance
	- set up snap shots for long-running reports during off-hours
