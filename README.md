Introduction
------------

This is an example of usage TService. TService is the test-service, a fake API that you can use to mock third-party API. It's developed lightweight, has no dependency on any programming language or framework.  It can define service slowness emulate service errors. Config or responses changes on the fly without any service restarting.

<p align="center"><img src="/assets/usage.gif?raw=true"/></p>


Installation and usage
-------------

To launch it, run:

    docker-compose up

You can also include the service in your existing compose using [docker hub's image](https://hub.docker.com/repository/docker/letniy/tservice)

```yml
tservice:
   image: docker.io/letniy/tservice:latest
   ports:
      - "8085:8085"
   volumes:
      - ./configs:/configs
   networks:
      app_net:
   entrypoint: ["/bin/app", "-config", "/configs/config.yml", "-responsePath", "/configs/responses", "-port", "8085"]
```

Configuration
-------------

An example of the configuration you can find in the configs directory.

License
-------

The TService package is licensed under the MIT. Please see the LICENSE file for details.