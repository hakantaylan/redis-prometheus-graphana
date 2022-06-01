# How to monitor Redis with Prometheus and Grafana | Docker
How to monitor Redis with Prometheus and Grafana | Docker

Run Docker Compose
```bash
docker-compose up
```
Check status of Prometheus and Redis Exporter
```bash
http://localhost:9090/targets
```
![Alt text](images/prometheus.png?raw=true "Prometheus")

Visit Grafana Dashboard

Default
```bash
User: admin
Password: admin
```
```bash
http://localhost:3000
```
![Alt text](images/graphana.png?raw=true "Graphana")

Add data source

![Alt text](images/graphana-add-datasource.png?raw=true "Graphana Add Datasource")

Save And Test

![Alt text](images/graphana-save-test.png?raw=true "Graphana Save And Test")

Import Redis Dashboard for Prometheus

For this we will use a Dashboard created by the community

![Alt text](images/graphana-import-dashboard.png?raw=true "Graphana Import DashBoard")

https://grafana.com/grafana/dashboards/763

Import JSON of code

![Alt text](images/graphana-import-dashboard2.png?raw=true "Graphana Import DashBoard2")

![Alt text](images/graphana-import-dashboard3.png?raw=true "Graphana Import DashBoard3")

Code: 763

JSON:
https://grafana.com/api/dashboards/763/revisions/3/download

Dashboard

![Alt text](images/graphana-final.png?raw=true "Graphana Dashboard Final")

Eğer Redis'e data populate etmek istersen
```bash
docker exec -it redis-container-id-or-name sh
```
```bash
redis-cli -h hostname-or-ip -p port -u user-name -a authenticaiton-password şeklinde bağlanılıyor!!! 
```
```shell
127.0.0.1:6379> ping
PONG
127.0.0.1:6379> set name mark
OK
127.0.0.1:6379> get name
"mark"
127.0.0.1:6379> incr counter
(integer) 1
127.0.0.1:6379> incr counter
(integer) 2
127.0.0.1:6379> get counter
"2"
127.0.0.1:6379> exit
# exit
```
