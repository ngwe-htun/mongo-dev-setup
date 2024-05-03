
## Usage

#### Requirements
- Docker
- Docker Compose
---

#### Local `.env`
- Copy from `.env.example`
  ```
  cp .env.example .env
  ```
- Modify `.env` variables as needed
---

#### Preparation
*Need to create as I want to use as external instead of docker compose auto generate*
- Docker network
  - Create docker network
    ```
    docker network create dev-network
    ```
  - Verify it
    ```
    docker network ls | grep dev-network
    ```

- Docker volume
  - Create volume
    ```
    docker volume create mongo-db
    ```
  - Verfiy it
    ```
    docker volume ls | grep mongo-db
    ```
---

#### Running
- Change directory
  ```
  cd mongo-dev-setup
  ```
- Running
  ```
  docker compose up -d
  ```
- Verify it
  ```
  docker compose ps
  ```
---

#### Using `mongosh`
- Run a command inside container
  ```
  docker compose exec mongo /bin/bash
  ```
- Connect with username and password you set
  ```
  mongosh --username username_here 
  ```
  - Eg
    ```
    mongosh --username admin
    ```
---

#### Using `mongo express`
- Inspect the port that you expose
  ```
  docker ps
  ```
- Open in browser  
  *Replace with your port*
  ```
  localhost:8081
  ```
---

#### Cleaning up
- Stop the services
  ```
  docker compose down
  ```
- Remove docker network
  ```
  docker network rm dev-network
  ```
- Remove docker volume
  ```
  docker volume rm mongo-db
  ```
- Remove docker images used by the services  
  *Bash*
  ```
  docker rmi -f $(docker images -a | grep mongo | awk '{print $3}')
  ```
---

> Happy coding