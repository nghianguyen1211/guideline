# Development guideline
## New member guildline
#### Working softwares
- Communication: (Microsoft) [Skype](https://www.skype.com/en/get-skype/) for chatting and Outlook for email
- Office: Microsoft 360 Office
- [Java JDK 8](https://www.oracle.com/java/technologies/javase-jdk8-downloads.html)
- GIT version control ([Sourcetree](https://www.sourcetreeapp.com/) or ...)
- IDE ([IntelliJ](https://www.jetbrains.com/idea/download/), [Netbeans](https://netbeans.apache.org/download/index.html) or ...)
- Databases clients:
  - Mongodb [Compass Community Edition](https://www.mongodb.com/download-center/compass)
  - MySQL [Workbench](https://dev.mysql.com/downloads/workbench/).
- Service test client:
  - [SoapUI Open Source](https://www.soapui.org/downloads/soapui.html)
  - [Postman](https://www.postman.com/downloads/)
- UML tool [Visual Paradigm Community Edition](https://www.visual-paradigm.com/download/community.jsp)
- FTP client [FileZilla](https://filezilla-project.org/download.php)
#### Team communication
We commumicate through Skype and email mostly. Please ask your mentor to add you to your team group if he/she forgot.
#### Working process
Jira is the popular tool for software development management. Ask the IT Helpdesk to send an invitation email for you if they forgot.
#### SSH Key
You need to provide your unique SSH key for our System Operators (SO) to allow you access the internal system through SSH channel. If you are not sure how to create please check the [guide line](https://docs.gitlab.com/ee/ssh/).

*And the last one. If you're free and bored :D Ask your line manager for tasks...*
## README guideline
```
# *Version v2.x.y*
[l](url)
```
With:
- lt: (Jira task, bug) link
- url: url of the link
- x: sprint number
- y: counter value
## REST API guideline
### Identify resources  
1. Resource must be a noun.  
*Non-compliant*
```
POST /phones/0901234567/signup
POST /accounts/1/signin
```
*Compliant*
```
POST /accounts
{"phone": "0901234567"}
POST /oauth/access_token
{"account": "1"}
```
2. Resource patterns:
- Collection `/%resource_name%s` for search or insertion.
- Singleton `/%resource_name%s/%id%` for getting, updating or deleting a unique resource based on its id.
- Property of a resource `/%resource_name%s/%id%/propertyName` for insertion, getting, updating or deleting a property of the unique resource based on its id.

### Support methods
Name | Operation
---- | --------
POST | Insert
PUT | Replace (Update all)
PATCH | Update partial
GET | Select (list or exactly one)
DELETE | Remove

### Versioning
Use URI versioning.  
*Non-compliant*
```
/1/accounts
/v1.0/accounts
```
*Compliant*
```
/v1/accounts
/v2/accounts
```

*References*
- [Microsoft API Guidelines](https://github.com/microsoft/api-guidelines/blob/vNext/Guidelines.md)
- [Google API Guidelines](https://cloud.google.com/apis/design/resources)

## IAC-Processor configuration
### Add new caller&key in [service] section if not exist
### Add new value in list value in [noti-types] section
### Add new config section
### Queue names
- dev: IN_APP_NOTIFICATION_V2
- test: IN_APP_NOTIFICATION_V2_TEST
### Queue payload:
```
{
	"reqId": "...",
	"caller": "...",
	"data": {
		"type": "",
		"walletId": "...",
		"phone": "xxx",
		"title": "...",
		"body": "..."
	}
}
```
