### React application with a NodeJS backend and a MySQL database

Project structure:
```
.
├── backend
│   ├── Dockerfile
│   ...
├── db
│   └── password.txt
├── docker-compose.yaml
├── frontend
│   ├── ...
│   └── Dockerfile
├── .env
└── README.md
```

[_docker-compose.yaml_](docker-compose.yaml)
```
services:
  backend:
    build: backend
    ports:
      - 80:80
      - 9229:9229
      - 9230:9230
    ...
  db:
    image: mysql:8.0.19
    ...
  frontend:
    build: frontend
    ports:
    - 3000:3000
    ...
```
The compose file defines an application with three services `frontend`, `backend` and `db`.
When deploying the application, docker-compose maps port 3000 of the frontend service container to port 3000 of the host as specified in the file.
Make sure port 3000 on the host is not already being in use.


After the application starts, navigate to `http://localhost:3000` in your web browser.


The backend service container has the port 80 mapped to 80 on the host.

