Telecom Data Analysis using Kafka, Kibana
Engined a real-time streaming pipeline that processed and
analyzed telecom call data records using MySQL, Airflow and
Kafka, enabling real-time analysis in Kibana and reducing data processing latency by 40%.
Implemented Slack notifications, achieving a 50% reduction in
issue resolution times and enhancing operational efficiency. 

## installation guide
    $ docker-compose up -d
    
    for elk and kibana go to docker_elk dir and run below command
    
    $ docker-compose up -d

## upload connector(confluent connector 8083 port)
    copy dokcer-id of cnfldemos/cp-server-connect-datagen:0.5.0-6.2.0 container  like below
    05a5dd32da60   cnfldemos/cp-server-connect-datagen:0.5.0-6.2.0   "/etc/confluent/dock…"   About an hour ago   Up 2 minutes        0.0.0.0:8083->8083/tcp, 9092/tcp                 connect        

    $ docker cp .\connector\debezium-debezium-connector-mysql-1.7.1\ 05a5dd32da60:/usr/share/confluent-hub-components

    $ docker cp connector/confluentinc-kafka-connect-elasticsearch-11.1.7 05a5dd32da60:/usr/share/confluent-hub-components

    and restart docer container 
     $ docker-compose restart

## change your ip add in connector-json(both mysql and elk connector)  (ipconfig)
    192.168.48.1->yourIp

## create index in kibana(search kibana index in search bar)
    device_datasets,service_datasets,call_datasets

## search object in kibana search and upload 
    graph/telecom-analysis.ndjson


## f8cf3f001111
## 192.168.0.8
