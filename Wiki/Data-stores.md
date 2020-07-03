

# Data stores

The app uses the following data store:

All these resources are created in your Azure subscription. None are hosted directly by Microsoft.

- **Azure Table Storage**
    - [AcquiredSkillEntity] to store skills added by owner of project.
    - [ProjectEntity] to store project related details. 
    - [TeamSkillEntity] to store tags information configured for different teams.
    - [UserMembershipEntity] to store user team membership data for further validating the user's identity.

## Storage account tables

**1. AcquiredSkillEntity**

The table has following rows:

|Attribute|Comment |
|--|--|
|UserId| Azure Active Directory Id of user.|
|ProjectId| Unique identifier for each created project.| 
|CreatedDate| Date time when participant acquired the skills.|
|AcquiredSkills| Semicolon separated list of skills acquired by participant.|
|Feedback| Feedback given by project owner to a participant.|
|ProjectTitle| Project title.|
|ProjectOwnerName| Name of user who created the project. | 
|ProjectClosedDate| Date time when project is closed. |

**2. ProjectEntity**

The table has following rows:

|Attribute|Comment |
|--|--|
|PartitionKey| Azure Active Directory Id of user.|
|RowKey|Post Id (GUID) – unique identifier for each created post. | 
|Status| Project status like Active/New.|
|Title| Project title.|
|Description| Project description.|
|SupportedDocumentLinks|URL's of the supported documents. |
|RequiredSkills| Semicolon separated skills entered by owner.|
|StartDate| Start date time of project.|
|EndDate| End date time of project.|
|CreatedDate| Date time when project is created.|
|CreatedByName| Name of user who created the project.|
|UpdatedDate| Date time when project is updated.|
|UserId| Azure Active Directory id of user who created the project.|
|TeamSize| Team size of a project|
|IsRemoved| Value indicating whether the project is deleted or not.|



**3. TeamSkillEntity**

The table has following rows:

|Attribute|Comment |
|--|--|
|PartitionKey| Team Id where bot is installed.|
|RowKey| Team Id where bot is installed.|
|TeamId| Unique value for each Team where skills has configured.|
|UserAadId| Azure Active Directory id of user who configured the skills in team.|
|Skills| Semicolon separated skills selected by user.|
|CreatedByName| User name who configured skills in team.|
|BotInstalledOn| Date time when the application is installed.|

**4. UserMembershipEntity**

The table has following rows:

|Attribute|Comment |
|--|--|
|PartitionKey| User's Azure Active Directory Id.|
|RowKey| User's Azure Active Directory Id.|
|UserAadObjectId| User's Azure Active Directory Id|
|UserConversationId| User's Conversation Id.|
|ServiceUrl| Service Url.|

**5. TeamConfiguration**

The table has following rows:

|Attribute|Comment |
|--|--|
|PartitionKey| Team Id where bot is installed.|
|RowKey| Team Id where bot is installed.|
|BotInstalledOn| Date when bot was installed in Team.|
|ServiceUrl| Service Url.|
|TeamId| Team Id where bot is installed.|