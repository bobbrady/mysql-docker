# mysql-docker
A simple MySQL Docker project

## Usage

The MySQL server container is instantiated with docker-compose:
```bash
docker-compose up
```

The default settings are configured in the docker-compose.yml file:
* MySQL version: 8.0 GA Latest Stable
* MySQL root password: 'password'
* MySQL data directory: ./mysql-data created where command is issued
