# FlexFit Membership System

## Overview

FlexFit is a gym membership management system developed using a Flask REST API with a MongoDB Database. The frontend is built with HTML, CSS and JavaScript, and communicates with the backend through JSON API requests.

The application allows the gym owner to add the new member in their gym and add the name starting date and expiry date of membership and also show the persons whose membership is expiring soon upto 14 days.

Additional features include:

- Search members by name, email or phone number.
- Sort member records by different fields.
- Export all member information to a CSV file.
- Real-time dashboard statistics without refreshing the page.
- REST API backend that returns JSON responses.

## Deployment

This application is deployed on google cloud virtual machine and running live..

**Google Cloud VM**

https://console.cloud.google.com/compute/instances?authuser=1&facet_url=https:%2F%2Fcloud.google.com&project=project-c3dae712-2b9e-4569-b9a

**Live Application**

http://136.66.121.44/


## References

The following resources were used during development of the project.

### Stack Overflow

MongoDB connection management:

https://stackoverflow.com/questions/18650890/keeping-open-a-mongodb-database-connection

### ChatGPT

API endpoint implementation:

https://chatgpt.com/c/6a54934f-9d4c-83ee-aaad-01098504e231

CSV export functionality and CORS configuration:

https://chatgpt.com/c/6a549252-a6e4-83ee-9de0-3f24bb31d35f

### Claude AI

Development discussion:

https://claude.ai/share/7ebda95d-13a5-4a4a-a421-daa0a51af476

## AI Usage

Claude AI was used to help generate a project template and basic CRUD . These were then reviewed, modified and extended to meet the assignment requirements.
i also stuck on mongodb connection i also get information and help from claude AI and by the help of youtube video i sorted this issue and it took 4 hours to resolve and now i am familiar with this i used the mongodb and python first time.

The following parts of the project are listed below who was done by AI and i make some changes to understand the logic and i also make many errors in the project by making changes in javascript validations and Api's and then sorted with the help of AI and understand how they working .

- Form validation
- CSV export functionality
- MongoDB query logic
- Search using `$regex` and `$or`
- Dashboard aggregation, including upcoming membership expiry statistics
- Frontend JavaScript for sorting and dynamically updating the interface
- Testing and debugging
