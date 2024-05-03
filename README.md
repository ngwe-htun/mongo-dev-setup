
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

#### Docker volume
- Create volume
  ```
  docker volume create mongo-db
  ```
- Verfiy
  ```
  docker volume ls | grep mongo-db
  ```

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
