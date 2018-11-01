# Docker-compose files for a simple uptodate: InfluxDB + Grafana + Telegraf

## Prepare

```bash
mkdir -p ~/docker/influxdb/data
mkdir -p ~/docker/telegraf/data
mkdir -p ~/docker/grafana/data; chown 472:472 ~/docker/grafana/data
```

## Run

```
git clone https://github.com/sejnub/docker-influxdb-grafana.git
cd docker-influxdb-grafana

docker-compose up -d
```

Show me the logs:
```
docker-compose logs
```

Stop it:
```
docker-compose stop
docker-compose rm
```

Update it:
```
git pull
docker pull grafana/grafana
docker pull influxdb
docker pull telegraf
```

If you want to run Telegraf, edit the telegraf.conf to yours needs and:
```
docker exec telegraf telegraf
```
