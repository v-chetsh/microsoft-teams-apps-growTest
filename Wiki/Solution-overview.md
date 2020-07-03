

# Solution overview


Grow app provides platform for employees to discover & contribute to projects or volunteer activities thereby learn new stuff based upon the competencies required and qualifications.

**Grow Bot:** This is a web application built using the [Bot Framework SDK v4 for .NET](https://docs.microsoft.com/en-us/azure/bot-service/bot-service-overview-introduction?view=azure-bot-service-4.0) and [ASP.NET Core 2.1](https://docs.microsoft.com/en-us/aspnet/core/?view=aspnetcore-2.1). Grow is a BOT that  builds a competitive environment in the team for employees to actively participate and contribute through leaderboard. Drive engagement and participation by sharing new opportunities in the channel.

**Azure solution**  
- The app service implements the bot and messaging extension experience by providing end points for user communication. The app service hosts the react app in order to display posts shared by users through tab. User can add/update and delete projects, join a project and can acquire skills.
- App endpoint is registered as messaging end point in bot registration portal and provides an endpoint /api/messages to process bot and messaging extension requests/response.
- App service hosts React application for tabs and provides custom APIs in back end for fetching and storing data securely.
- Single Sign On experience is implemented in React application for seamless user authentication.

**Azure bot service:** Azure bot service is developed using BOT SDK v4. Grow Your Skills web app endpoint is registered as messaging end point in bot registration portal.

**Azure table storage**  
- Azure table storage is used to store project details and user configuration values. Details are provided in section  [Data stores](https://msteams-captain.visualstudio.com/xGrowth%20App%20Templates/_git/msteams-app-goodreads?path=%2FWiki%2FData-store.md&version=GBv-sals%2FDocumentation&_a=preview).

**Azure search service** 
- Leaveraging querying and indexting capabilities of Azure search service for faster retrieval of projects as per user demand. It provides robust queries over indexed data which overcomes query limitation of table storage.

**Application Insights:** Application insights is used for tracking and logging. Details are provided in section [Telemetry](/wiki/Telemetry.md).

**Data stores:** The web app is using Azure table storage for data storage due to its cost-effective pricing model and providing support for No-SQL data models.