# Development guideline
## New member guildline
#### Team communication
We commumicate through Skype and email mostly. Please ask your mentor to add you to your team group if he/she forgot.
#### Working process
Jira is the popular tool for software development management. Ask the IT Helpdesk to send an invitation email for you if they forgot.
#### SSH Key
Here is the [guide line](https://docs.gitlab.com/ee/ssh/) to create ssh key.

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
