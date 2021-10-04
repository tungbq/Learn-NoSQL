# Learn-NoSQL

# Start server
`docker compose up` or `docker compose -f docker-compose.yaml up`

# Stop server
`docker compose stop`
# Start server again
`docker compose start`

# Destroy all containers
`docker compose down`

# To check docker container status
`docker ps`

# Debug in docker
## Start container first: `docker exec -it mongodb bash`
## Then use mongo shell: `mongo mongodb://localhost:27017 -u rootuser -p rootpass` (27017 is the port inside container)

