# Load Balancer
This repository contains the settings for the __load balancer__. The load balancer is based on `nginx`. It accepts two instances of the backend engine named as `back1` and `back2`. It exposes the web service on port 5000. One of the backend servers are marked as `backup` according to the assignment requirements. The server requires both `back1` and `back2` to be running.


## Run without Docker
Use `start nginx` command to start nginx.


## Run with Docker
1. Build the Docker image using
```
$ docker build -t ds/lb .
```

2. Run the docker image using
```
$ docker run -p 5000:5000 --link back1 --link back2 --rm -it ds/lb
```
This command exposes the port 5000 on the host system. The backend servers are linked via the `--link` argument; this container requires the backend server to be ran as `back1` and `back2` (by providing the `--name back1` argument to the backend server run command). If you wish to change these names, don't forget to edit the `nginx.conf` file accordingly. 
