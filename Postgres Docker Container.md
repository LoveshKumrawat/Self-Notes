# **Postgres Docker Container**
<br>

> **Install Docker**

	sudo apt install docker.io
---
> **To use Docker commands as a normal user `(Without sudo)`**

	sudo usermod -aG docker ${USER}
	newgrp docker
	sudo chmod -R 777 /var/run/docker.sock
---
> **Downloads the Postgres image from Docker-Hub**

	docker pull postgres
---
> **Creates a new Container from the downloaded `postgres` image, without starting it**

	docker create postgres
---
> **List the created images**

	docker images
---
> **Run the `postgres` Container**

	docker run --name pgsql -e POSTGRES_PASSWORD=password -p 5432:5432 -v ~/pgsql-vol:/var/lib/postgresql/data -d postgres

- **`--name`** *Name of the Container `(Eg: pgsql)`*
- **`-e`** *Set Environment Variables like:*
	- **`POSTGRES_PASSWORD` : Mandatory** *Password for the Container `(Eg: password)`*
	- **`POSTGRES_USER` : Optional** *User name for the Container `(Default: postgres)`*
	- **`POSTGRES_DB` : Optional** *DB name for the Container `(Default: POSTGRES_USER)`*
	- **`PGDATA` : Optional** *DB default local/remote location for the Container `(Default: /var/lib/postgresql/data)`*
- **`-p`** *Defines **localPORT**`(Eg: 5432)`**:imagePORT**`(Default: 5432 for postgres)`*
- **`-v` : Optional** *Mount Volume for the Container **localDir**`(Eg: ~/pgsql-vol)`**:PGDATA**`(Default: /var/lib/postgresql/data)`*
- **`-d | --detach` : Optional** *Run the Container in background*
---
> **Copy DB to Local Directory**

	docker cp pgsql:/var/lib/postgresql/data <localDir>
---
> **Shows the Process Status of Running Containers**

	docker ps
---
> **Shows the Process Status of All existing Containers**

	docker ps -a
---
> **Opens the Bash of running `postgres` Container**

	docker exec -it pgsql bash

- **`exec`** *Helps to run a new command in a running container at default directory of the container*
- **`-i | --interactive`** *Keep STDIN open even if not attached*
- **`-t | --tty`** *Allocate a pseudo-TTY*
---
> **Connection to the `postgres` DB's**

	psql -h localhost -U postgres --dbname=postgres

OR

	su - postgres
	psql --dbname=postgres

- **`--dbname` : Optional** *Default connection to the given existing DB `(Default: postgres)`*
---
> **Install `psql` for Remote access to DB**

	sudo apt install postgresql
---
> **Remote access to DB**

	psql -h <IPAddress> -p <port> -U postgres
---