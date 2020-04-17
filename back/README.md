# Start Trek Wiki Backend

## Setting up and running local database

Make sure you have Docker installed and running.

Pull mongo image from docker
`docker pull mongo`

Run the docker mongo image
`docker run -d -p 27017:27017 --name startrek-wiki mongo -v /data/db:/data/db`

`docker run -d` Here, we are running the docker container with a detached mode. there are two mode to run docker container. one is detached and another one is interactive mode. detached mode will run in background whereas interactive mode runs in the foreground(terminal will be active). Problem with interactive mode is if you close the terminal, container will stop running.

`-p 27017:27017` Here, -p represents the port of the container. you can map the port of the container and your machine port to communicate with the container. As MongoDB always run in port 27017, we map the ports here.

`--name startrek-wiki mongo` After that, we added flag --name which represents the docker container name.

`-v /data/db:/data/db` Lastly, we mount the volume of docker container and local machine volume. This is one of the important commands in the whole part. This command mounts the volume of docker container db directory and local machine db directory so that, you won't lose your database data even after restarting the container.
