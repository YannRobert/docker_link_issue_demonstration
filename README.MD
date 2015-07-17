This repo is intended to serve as support for an issue in https://github.com/docker

docker-compose is used to run a stack of containers.
featuring a webserver, and a proxy to the webserver.

When using Docker 1.6, the container stack works as expected.
When using Docker 1.7, the container stack fails to work as expected.


usage:
```
docker-compose kill && docker-compose rm --force && docker-compose up
```

then:
```
curl http://localhost:8000
```
will print the expected ```hello world``` in any case.

but :
```
curl http://localhost:8888
```
will print immediatly the expected ```hello world``` with docker version 1.6, but will fail after about 7 seconds with an error ```503 Service Unavailable``` with docker version 1.7


This has been verified with both docker-compose version ```1.2.0``` and ```1.3.3```

