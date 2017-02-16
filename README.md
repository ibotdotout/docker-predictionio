# Update by [@ibotdotout](http://github.com/ibotdotout)

[![](https://badge.imagelayers.io/ibotdotout/docker-predictionio:latest.svg)](https://imagelayers.io/?images=ibotdotout/docker-predictionio:latest
'Get your own badge on imagelayers.io')

* Update to Prediction.io version 0.10.0 [steveny2k/docker-predictionio](https://github.com/steveny2k/docker-predictionio)
* Reduce Image Size from 2Gb to 1.3 Gb

# PredictionIO docker container
Docker container for PredictionIO-based machine learning services

[![Docker build](http://dockeri.co/image/sphereio/predictionio)](https://registry.hub.docker.com/u/sphereio/predictionio/)


[PredictionIO](https://prediction.io) is an open-source Machine Learning
server for developers and data scientists to build and deploy predictive
applications in a fraction of the time.

This container uses Apache Spark, HBase and Elasticsearch.
Use it interactively for development:

```Bash
$ docker run -it -v $HOME/MyEngine:/MyEngine sphereio/predictionio /bin/bash
```

Or create your own deployable docker container:

```Dockerfile
FROM sphereio/predictionio

ADD MyEngine /MyEngine

EXPOSE 8000

ADD run.sh /run.sh

ENTRYPOINT /run.sh
```

and run.sh:

```Bash
#!/bin/bash

set -e

pio-start-all
cd /MyEngine
pio build --verbose
pio deploy
```
