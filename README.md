# mysql-docker

This repo provides a MySQL Docker container instance for development purposes. It utilizes basic best practices and could be used as a starting point for a production instance. Features included:

- Best practice: Docker managed volume for persisted MySQL data
- Best practice: Bind mounted my.cnf config file for user managed configuration settings
- Best practice: non-root "service" DB user created with empty start service database.
- Best practice: Full UTF-8 support configuration
- Passords and other initialized environment variables loaded from .env file
- Named bridge network used for future extensibility as other app containers added to services

## Usage

```shell
git clone https://github.com/bobbrady/mysql-docker.git
cd mysql-docker
# Edit ./.env to set paswords and database/user names to your liking
# Edit ./my.cnf to customize the MySQL configuration to your liking
docker-compose up
# Get container shell as root and verify starter database was created
docker exec -it mysql-db bash
root@79d370eb0a0f:/# mysql -p -e "SHOW DATABASES"
#
Enter password:
#+--------------------+
#| Database           |
#+--------------------+
# information_schema |
#| mysql              |
#| performance_schema |
#| testdb             |
#+--------------------+
```

This repo was successfully tested with the mysql:latest image (v8.0.29) on Mac Intel Monterey.

Feel free to create an issue if any problems or improvements are identified.
