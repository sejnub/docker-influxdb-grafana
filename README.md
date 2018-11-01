# Docker-compose files for a simple uptodate: InfluxDB + Grafana + Telegraf

## Prepare

```bash
cd ~
mkdir -p ~/docker-influxdb-grafana/influxdb/data
mkdir -p ~/docker-influxdb-grafana/telegraf/data
mkdir -p ~/docker-influxdb-grafana/grafana/data; chown 472:472 ~/docker/grafana/data
```

## Run

```
cd ~
git clone https://github.com/sejnub/docker-influxdb-grafana.git
cp ./telegraf.conf ~/docker-influxdb-grafana/telegraf/data
cd docker-influxdb-grafana

docker-compose up -d
```

Show me the logs:
```
cd ~/docker-influxdb-grafana
docker-compose logs
```

Stop it:
```
cd ~/docker-influxdb-grafana
docker-compose stop
docker-compose rm
```

Update it:
```
cd ~/docker-influxdb-grafana
git pull
docker pull grafana/grafana
docker pull influxdb
docker pull telegraf
```

If you want to run Telegraf, edit the telegraf.conf to yours needs and:
```
cd ~/docker-influxdb-grafana
docker exec telegraf telegraf
```
