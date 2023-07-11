## Домашнее задание к занятию "`Prometheus. Часть 2`" - `Стрекозов Владимир`
---
### Задание 1 
#### Погасите node exporter, стоящий на мониторинге, и прикрепите скриншот раздела оповещений Prometheus, где оповещение будет в статусе Pending
#### {Файл с настройками уведомления](https://github.com/Svalker1989/hw-05/blob/main/alertmanager_notification_file.yml)
##### Результат добавления уведомления в prometheus
![](https://github.com/Svalker1989/hw-05/blob/main/Z1.PNG)
### Задание 2
#### Прикрепите скриншот Alerts из Prometheus, где правило оповещения будет в статусе Fireing, и скриншот из Alertmanager, где будет видно действующее правило оповещения
#### Правило оповещения в статусе Fireing
![alt text](https://github.com/Svalker1989/hw-05/blob/main/Z1.PNG)
#### Действующее правило оповещения
![alt text](https://github.com/Svalker1989/hw-05/blob/main/Z2_2.PNG)
### Задание 3
#### Приложите скриншот браузера с открытым эндпоинтом (docker container), а также скриншот списка таргетов из интерфейса Prometheus.
#### эндпоинт (docker container)
![alt text](https://github.com/Svalker1989/hw-05/blob/main/Z3_1.PNG)
#### Cписок таргетов из интерфейса Prometheus
![alt text](https://github.com/Svalker1989/hw-05/blob/main/Z3_2.PNG)
### Задание 4*
#### Приложите скриншот, на котором будет дашборд Grafana с действующей метрикой
#### дашборд Grafana с действующей метрикой
![alt text](https://github.com/Svalker1989/hw-05/blob/main/Z4.PNG)

## PS
### [Файл сервиса prometheus](https://github.com/Svalker1989/hw-05/blob/main/prometheus.service)
### Команда --web.enable-lifecycle используется для перезапуска prometheus с помощью curl -X POST 192.168.0.162:9090/-/reload
## Часть конфига Prometheus.yml Alertmanager
```
alerting:
alertmanagers:
- static_configs:
- targets: # Можно указать как targets: [‘localhost”9093’]
- localhost:9093
```
## Мониторинг Docker в Prometheus
### Создать файл sudo nano /etc/docker/daemon.json
```
{
"metrics-addr" : "ip_нашего_сервера:9323", #ip адрес docker сервера:порт любой
"experimental" : true
}
```
