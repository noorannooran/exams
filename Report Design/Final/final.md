# Final Exam Review
- Modules 8, 9, 10, 11 and 12
- (Report-Authoring Practices slides 25-33).

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
