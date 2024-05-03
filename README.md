
## Usage

#### Requirements
- Docker
- Docker Compose

#### Docker network
- Create docker network
  ```
  docker network create dev-network
  ```
- Verify
  ```
  docker network ls | grep dev-network
  ```
---

#### Docker volume
- Create volume
  ```
  docker volume create mongo-db
  ```
- Verfiy
  ```
  docker volume ls | grep mongo-db
  ```
---

#### Running
- Change dir
  ```
  cd mongo-dev-setup
  ```
- Running
  ```
  docker compose up -d
  ```
- Verify
  ```
  docker compose ps
  ```
---

#### Using mongosh
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