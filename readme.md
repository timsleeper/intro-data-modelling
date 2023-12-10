#### Installing Docker
`brew install docker`

#### Using a named volume to store Postgres data
`docker volume create {name-of-volume}`
or
`-v {name-of-volume}:{volume-storage-location}`
`-v local_psql_data:/var/lib/postgresql/data`

#### Specifying a port to expose
`-p {desired-port}:5432`
`-p 54320:5432`

#### Specifying a password for Postgres
`-e POSTGRES_PASSWORD={desired-password}`
`-e POSTGRES_PASSWORD=my_password`

#### Running Postgres in Docker Container
`docker run --name {name-of-container} -v {name-of-volume}:{volume-storage-location} -p {desired-port}:5432 -e POSTGRES_PASSWORD={desired-password} -d {desired-postgres-image}`

`docker run --name local-psql -v local_psql_data:/var/lib/postgresql/data -p 54320:5432 -e POSTGRES_PASSWORD=my_password -d postgres`


#### Is it running?
- Check the logs:
`docker logs {name-of-container}`
`docker logs local-psql`

- List of current containers:
`docker ps`
`docker ps -a`
`docker ps --last 1`

- Connecting:
`psql -h localhost -p {desired-port} -U postgres`
`docker exec -it {name-of-container} psql -U postgres`
- `ctrl-d` or `exit` to exit

#### Starting or stopping the container:
`docker start/stop {name-of-container}`

#### Passing commands
`docker exec -it {name-of-container} {command}`
`docker exec -it {name-of-container} psql -U postgres -c "{command}"`
