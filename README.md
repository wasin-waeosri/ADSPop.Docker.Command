# Running ADS Pop with Docker

ADS POP is ```a cut down RTDS in a single application``` that gives developers and small infrastructure to run the RTDS system for the development phase.

This project is just my record of the commands to run ADS Pop with Docker and Docker Compose.

## Prerequisite

This project requires the following dependencies software and libraries.
1. [Docker Desktop/Engine](https://docs.docker.com/get-docker/) application.
2. The ADS license
3. Access to Refinitiv Real-Time - Optimized. (If you are sourcing your real-time data from an internal ADS, this step is not required)
4. Internet connection. 

I highly recommend you check my colleagues' articles about the step-by-step guides set up and run in RTC (or ADS Pop) in Docker before proceeding.
* [Testing Real-time Streaming applications with Docker & Refinitiv Real-Time Connector (part 1)](https://developers.refinitiv.com/en/article-catalog/article/testing-real-time-apps-with-docker-and-real-time-connector)
* [Testing Real-time Streaming applications with Docker & Refinitiv Real-Time Connector (part 2)](https://developers.refinitiv.com/en/article-catalog/article/testing-real-time-apps-with-docker-and-real-time-connector-2)
* [Configuring adspop docker to connect to Refinitiv Real-Time Optimized](https://developers.refinitiv.com/en/article-catalog/article/introduction-to-the-refinitivrealtime-adspop-docker-image)

## Build Docker and Run

```
$> docker-compose up
```

## Run Docker

``` bash
$> docker-compose --env-file .env run --service-ports -d --name adspop adspop
```
Alternatively, using a shell script:

``` bash
$> ./start_ads_compose_detach.sh
```
## Access Docker ADS

``` bash
$> docker exec -ti adspop /bin/bash
```
Alternatively, using a shell script:

``` bash
$> ./access_ads_docker.sh
```

## Stop and Remove Docker ADS container

``` bash
$> docker stop adspop
$> docker rm adspop
```

## Changing ADS Version.

The ADS version configuration is available in a ```.env``` file. You can check the version/tag from the [refinitivrealtime/adspop DockerHub](https://hub.docker.com/r/refinitivrealtime/adspop/tags) website.

```
VERSION=3.6.1.L1
```

## Reference

* [Testing Real-time Streaming applications with Docker & Refinitiv Real-Time Connector (part 1)](https://developers.refinitiv.com/en/article-catalog/article/testing-real-time-apps-with-docker-and-real-time-connector)
* [Testing Real-time Streaming applications with Docker & Refinitiv Real-Time Connector (part 2)](https://developers.refinitiv.com/en/article-catalog/article/testing-real-time-apps-with-docker-and-real-time-connector-2)
* [Configuring adspop docker to connect to Refinitiv Real-Time Optimized](https://developers.refinitiv.com/en/article-catalog/article/introduction-to-the-refinitivrealtime-adspop-docker-image)
* [refinitivrealtime/rtc Docker](https://hub.docker.com/r/refinitivrealtime/rtc) page