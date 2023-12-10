### Running Postgres in Docker Container
`docker run --name {name-of-container} -v {name-of-volume}:{volume-storage-location} -p {desired-port}:5432 -e POSTGRES_PASSWORD={desired-password} -d {desired-postgres-image}`

`docker run --name local-psql -v local_psql_data:/var/lib/postgresql/data -p 54320:5432 -e POSTGRES_PASSWORD=my_password -d postgres`
