# **Docker Functionalities**
<br>

> **Host docker's remote access within a container**

- Docker's socket access modification (grant access to container's non-root users)

	```sh
	sudo chmod o+rw /var/run/docker.sock
	```

- Add the below volume mounts to the container

	- `/var/run/docker.sock:/var/run/docker.sock`
	- `$(which docker):/usr/bin/docker`

- Optionally, can set the below environment variable to connect with docker socket at container's custom location (below is the default location)

	- `DOCKER_HOST=unix:///var/run/docker.sock`

---
