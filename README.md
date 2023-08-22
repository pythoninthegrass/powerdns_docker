# powerdns_docker

Takes inspiration from the [Running PowerDNS in the local environment with PowerDNS-Admin](https://medium.com/@fhc.silv/running-powerdns-in-the-local-environment-with-powerdns-admin-d4872c793a9b) guide by [@uhernfr](https://github.com/uhernfr).

Updates `compose` syntax, adds error handling, moves creds to env vars, swaps out [interlegis/powerdns](https://hub.docker.com/r/interlegis/powerdns) for [pschiffe/pdns-mysql](https://hub.docker.com/r/pschiffe/pdns-mysql) -- former is [deprecated](https://github.com/interlegis/docker-pdnsadmin).

## Setup
* [Install Docker Compose](https://docs.docker.com/compose/install/)

## Quickstart
* Commands
    ```bash
    # create .env file and fill out
    cp .env.example .env

    # start containers
    docker compose up -d

    # stop containers
    docker compose stop

    # remove containers, volumes, and networks
    docker compose down -v
    ```
* Open PowerDNS Admin at `localhost:9393`
  * Or the remote hosts's IP address
* Create a new user
* Fill out the PDNS Settings
  * PDNS API URL (default: `http://172.28.1.11`)
  * PDNS API KEY (see: `PDNS_api_key`)
  * PDNS VERSION (default: `4.1.1`)

## TODO
* Test actual usage
* Issue template
* CI/CD

## Further Reading
[pschiffe/pdns-mysql - Docker Image | Docker Hub](https://hub.docker.com/r/pschiffe/pdns-mysql)

[bitnami/mariadb - Docker Image | Docker Hub](https://hub.docker.com/r/bitnami/mariadb)

[ngoduykhanh/powerdns-admin - Docker Image | Docker Hub](https://hub.docker.com/r/ngoduykhanh/powerdns-admin)

[Generic MySQL backend — PowerDNS Authoritative Server documentation](https://doc.powerdns.com/authoritative/backends/generic-mysql.html#default-schema)

[Authoritative Server Settings — PowerDNS Authoritative Server documentation](https://doc.powerdns.com/authoritative/settings.html#webserver-password)

