# FlexFit Membership System

## Overview

FlexFit is a gym membership management system developed using a Flask REST API with a MongoDB database. The frontend is built with HTML, CSS and JavaScript, and communicates with the backend through JSON API requests.

The application allows gym staff to manage member records by adding new members, updating existing information, deleting members and searching for records by name, email or phone number. All user input is validated before being stored in the database to help maintain accurate records.

The dashboard provides a quick overview of the membership database, including the total number of members, active memberships and expired memberships. It also highlights memberships that will expire within the next 14 days, making it easier for staff to identify members who may need to renew their membership.

Additional features include:

- Search members by name, email or phone number.
- Sort member records by different fields.
- Export all member information to a CSV file.
- Real-time dashboard statistics without refreshing the page.
- REST API backend that returns JSON responses.

---

## Deployment

The application was deployed on a Google Cloud virtual machine.

**Google Cloud VM**

https://console.cloud.google.com/compute/instances?authuser=1&facet_url=https:%2F%2Fcloud.google.com&project=project-c3dae712-2b9e-4569-b9a

**Live Application**

http://136.66.121.44/

---

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

---

## AI Usage

Claude AI was used to help generate an initial project template and basic CRUD examples. These were then reviewed, modified and extended to meet the assignment requirements.

The following parts of the project were primarily implemented or significantly customised by me:

- Form validation
- CSV export functionality
- MongoDB query logic
- Search using `$regex` and `$or`
- Dashboard aggregation, including upcoming membership expiry statistics
- Frontend JavaScript for sorting and dynamically updating the interface
- Testing and debugging
