# Load Balancer
This repository contains the settings for the __load balancer__. The load balancer is based on `nginx`. It accepts two instances of the backend engine named as `back1` and `back2`. It exposes the web service on port 5000. One of the backend servers are marked as `backup` according to the assignment requirements. 


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
