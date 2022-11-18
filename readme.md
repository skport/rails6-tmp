# Rails 6 project template
This is a template project for ruby 2.6 & rails 6.0.

- Docker Container Configuration
  - app
    - ruby & rails
  - db
    - mariadb
  - adminer
    - Database Management in PHP

## Usage
Move to docker directory:
```shell
cd ./docker/rails6-tmp
```

Create and start containers:
1. Copy the gemfile needed for docker build to the docker directory.
2. Execute docker-compose command.
3. Remove gemfiles that are no needed.
```shell
cp ../../rails/Gemfile* .; \
docker-compose up -d; \
rm Gemfile*;
```

After container creation is finished, start with `docker-compose up -d` only.

Execute an interactive bash shell on the app container:
```shell
docker exec -it rails6-tmp-app bash
```

View docker log
```shell
docker logs rails6-tmp-app
```

### Browsing Rails
Visit `http://localhost:3000/`.

### Browsing database 
Visit `http://localhost:8080/` and browse database with "adminer".
The password is set in compose.yml.
This is the easiest way to verify that the database is up and running.