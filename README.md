## Build Docker and Run

```
$> docker-compose up
```

## Run Docker

```
$> docker-compose run --service-ports -d --name adspop adspop
```
## Access Docker ADS

```
$> docker exec -ti adspop /bin/bash
```