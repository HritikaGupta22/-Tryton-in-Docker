# -Tryton-in-Docker

Tryton is an open-source enterprise resource planning (ERP) system designed to provide modular, scalable, and customizable solutions for businesses. It includes a robust set of features for managing accounting, inventory, sales, purchases, and project management. Written in Python, Tryton has a three-tier architecture with a client, server, and database, ensuring flexibility and performance. Its modularity allows businesses to add only the features they need, making it suitable for various industries. With strong community support and regular updates, Tryton is a reliable choice for organizations seeking an open-source ERP solution.

## Pre-requisites
1.A system with Docker installed and configured.
2. Basic knowledge of command-line tools.

## steps:

**Start a PostgreSQL instance**
```
docker run --name tryton-postgres -e POSTGRES_PASSWORD=mypassword -e POSTGRES_DB=tryton -d postgres
```
**Setup the database**
```
docker run --link tryton-postgres:postgres -e DB_PASSWORD=mypassword -it tryton/tryton trytond-admin -d tryton --all
```
**Start a Tryton instance**
```
docker run --name tryton -p 8000:8000 --link tryton-postgres:postgres -e DB_PASSWORD=mypassword -d tryton/tryton
```

## Video
https://github.com/user-attachments/assets/d73feaac-c2a5-4441-8f7a-191b86d7079a
