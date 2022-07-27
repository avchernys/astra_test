This is the test task for Astra Linux interview

Необходимо написать Vagrantfile который по команде vagrant up сделает следующее:
1) Запустит бокс Ubuntu 20.04 (https://app.vagrantup.com/generic/ ).
2) Внутри ВМ произойдет автоматическая установка docker и docker compose (используя ansible).
3) Внутри ВМ произойдет установка node exporter для Prometheus (используя ansible).
4) С помощью docker compose (docker-compose up, сам docker compose стоит дернуть так же через ansible) будет запущено 2 контейнера:
4.1) Первый контейнер с prometheus, который будет настроен на сбор метрик с node exporter из Ubuntu
4.2) Второй контейнер с grafana, которая будет предварительно преднастроена: в качестве datasource используется prometheus из соседнего контейнера, уже загружен dashboard 1860 (https://grafana.com/grafana/dashboards/1860), который визуализирует метрики полученные с node exporter
5) Контейнер с grafana должен экспозить 3000 порт контейнера в ВМ с убунту
6) Сама ВМ с убунту должна экспозить 3000 порт в хостовую машину
 
По итогу нужно, что бы после запуска ВМ и выполнения настройки можно было бы открыть в браузере localhost:3000 и обнаружить там Grafana, зайти в нее и увидеть внутри dashboard который визуализирует метрики запущенной ВМ

## Prerequisites 
You need to install Vagrant and VirtualBox before you start

## How to Run
`
vagrant up
`