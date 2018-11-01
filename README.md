# Docker-compose files for a simple uptodate: InfluxDB + Grafana + Telegraf

## Prepare

```bash
cd ~
sudo rm -rf ~/docker-influxdb-grafana

cd ~
git clone https://github.com/sejnub/docker-influxdb-grafana.git

cd docker-influxdb-grafana
mkdir -p ~/docker-influxdb-grafana/influxdb/data
mkdir -p ~/docker-influxdb-grafana/telegraf/data
mkdir -p ~/docker-influxdb-grafana/grafana/data; sudo chown 472:472 ~/docker-influxdb-grafana/grafana/data

cp ~/docker-influxdb-grafana/telegraf.conf ~/docker-influxdb-grafana/telegraf/data/

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
