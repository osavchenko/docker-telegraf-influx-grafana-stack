# Example Resource monitoring systems

This an example project to show the TIG (Telegraf, InfluxDB and Grafana) stack.

## Start the stack with docker compose

```shell
$ docker-compose up
```

## Public services

### Grafana
- URL: http://localhost:3000 
- User: admin 
- Password: admin

### nginx
- URL: http://localhost:8080 

## Run the PHP Example

There is a Symfony Demo app as an example. To prepare it run next commands:

```shell
docker compose exec php composer install
docker compose exec php bin/console d:m:m --no-interaction
```

To run the benchmark:

```shell
docker compose exec apache ab -n 100 -c 10 http://nginx/uk/blog/ && \
    docker compose exec apache ab -n 10 -c 1 http://nginx/uk/blog/ && \
    docker compose exec apache ab -n 100 -c 25 http://nginx/uk/blog/
```

To find examples, please check the `metrics-example` folder.
