# Development guideline
## New member guideline
#### Working softwares
- Communication: (Microsoft) [Skype](https://www.skype.com/en/get-skype/) for chatting and Outlook for email
- Office: Microsoft 360 Office
- FE:
  - Web:
    - IDE:
      - [Visual Studio Code](https://code.visualstudio.com/download)
- BE:
  - Java:
    - JDK:
      - [Java Oracle JDK 8](https://www.oracle.com/java/technologies/javase-jdk8-downloads.html)
      - [Java Oracle JDK 11](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html)
    - IDE:
      - [Netbeans](https://netbeans.apache.org/download/index.html)
- GIT version control
  - GUI Clients:
    - [Sourcetree](https://www.sourcetreeapp.com/)
- Databases clients:
  - Mongodb [Compass Community Edition](https://www.mongodb.com/download-center/compass)
  - MySQL [Workbench](https://dev.mysql.com/downloads/workbench/).
  - Postgresql [pgAdmin](https://www.pgadmin.org/download/).
- Test clients:
  - HTTP:
    - [SoapUI Open Source](https://www.soapui.org/downloads/soapui.html)
    - [Postman](https://www.postman.com/downloads/)
- UML tools:
  - [Visual Paradigm Community Edition](https://www.visual-paradigm.com/download/community.jsp)
- FTP clients:
  - [FileZilla](https://filezilla-project.org/download.php)
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
Resource must be a noun.  
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
Resource patterns:
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
*To be continued...*  
  
*References*
- [Microsoft API Guidelines](https://github.com/microsoft/api-guidelines/blob/vNext/Guidelines.md)
- [Google API Guidelines](https://cloud.google.com/apis/design/resources)
## SSH
### Save password
`ssh-copy-id user@host`
