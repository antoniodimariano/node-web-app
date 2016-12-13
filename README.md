![Docker logo](https://www.docker.com/sites/default/files/moby.svg)

##How to dockerize a Node.js web app.

*Freely based on https://nodejs.org/en/docs/guides/nodejs-docker-webapp/*

###Building the image

`
$docker build -t adimariano/node-web-app .
`

the image will now be listed by Docker

```
$docker image


REPOSITORY               TAG       IMAGE ID      CREATED             SIZE

adimariano/node-web-app  latest    da74223de17a  5 minutes ago       649.4 MB
```


###Run the image

```
$ docker run -p 49160:8080 -d adimariano/node-web-app

```

```
# Get container ID
$ docker ps

# Print app output
$ docker logs <container id>

# Example
Running on http://localhost:8080
```

```

docker ps
CONTAINER ID        IMAGE                     COMMAND             CREATED             STATUS              PORTS                     NAMES
72a231e04232        adimariano/node-web-app   "npm start"         7 minutes ago       Up 7 minutes        0.0.0.0:59260->8080/tcp   hopeful_sammet
```

###Test it

```
$ curl -i localhost:49160

HTTP/1.1 200 OK
X-Powered-By: Express
Content-Type: text/html; charset=utf-8
Content-Length: 12
Date: Sun, 02 Jun 2013 03:53:22 GMT
Connection: keep-alive

Hello world
```

