## Rapidly provision Oracle Fusion Middleware 12c Services
Project to rapidly provision an Oracle Fusion Middleware environment using Docker Compose.

### Pre-requisites
Docker Engine version 1.10.1, build 9e83765

Docker Compose version 1.7.0dev, build d551496

### Usage
To build your base images, use the following commands:
```
cd ~
git clone https://github.com/justinpaulthekkan/docker-compose-fmw.git ~/build

docker build --shm-size=1g --force-rm --rm=true --no-cache -t oracledb -f ~/build/database/Dockerfile.12.1.0.2.160119 ~/build/database
docker build --shm-size=1g --force-rm --rm=true --no-cache -t wccontent -f ~/build/wccontent/Dockerfile.12.2.1.0.160119 ~/build/wccontent
docker build --shm-size=1g --force-rm --rm=true --no-cache -t wcportal -f ~/build/wcportal/Dockerfile.12.2.1.0.0 ~/build/wcportal
docker build --shm-size=1g --force-rm --rm=true --no-cache -t wcsites -f ~/build/wcsites/Dockerfile.12.2.1.0.0 ~/build/wcsites
```

Oracle WebCenter Content 12c:
```
# Create and start the containers
docker-compose -p demo1 -f ~/build/wccontent.yaml -d up

# Remove the stopped containers
docker-compose -p demo1 -f ~/build/wccontent.yaml -d rm
```

Oracle WebCenter Portal 12c:
```
# Create and start the containers
docker-compose -p demo1 -f ~/build/wcportal.yaml -d up

# Remove the stopped containers
docker-compose -p demo1 -f ~/build/wcportal.yaml -d rm
```

Oracle WebCenter Sites 12c:
```
# Create and start the containers
docker-compose -p demo1 -f ~/build/wcsites.yaml -d up

# Remove the stopped containers
docker-compose -p demo1 -f ~/build/wcsites.yaml -d rm
```
