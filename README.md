# pgadmin

PhpPgAdmin running in a container to easy maintain a Postgres database

# Start

I mostly use docker-compose.yml to integrate pgadmin into the stack. Of course the stack needs a Postgres container!

  pgadmin:
    restart: always
    container_name: pgadmin_container
    build: ./dockerfiles/pgadmin/
    environment:
        - POSTGRES_HOSTNAME=hostname
        - POSTGRES_HOST=db
        - POSTGRES_PORT=5432
        - POSTGRES_DEFAULTDB=dbname
        - APACHE_SERVERNAME=pgadmin
    ports:
      - "8000:80"
    links:
      - db



