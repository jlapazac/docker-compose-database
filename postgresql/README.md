docker run -d \
	--name some-postgres \
	-e POSTGRES_PASSWORD=mysecretpassword \
	-e PGDATA=/var/lib/postgresql/data/pgdata \
	-v /custom/mount:/var/lib/postgresql/data \
	postgres

# Fuente
https://www.postgresqltutorial.com/postgresql-getting-started/postgresql-sample-database/
https://hub.docker.com/_/postgres