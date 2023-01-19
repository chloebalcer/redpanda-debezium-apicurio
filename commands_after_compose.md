Check the available plug-ins to verify if Debezium for Postgres has been installed as expected:
---

$ curl -sS localhost:8083/connector-plugins

Register the connector with the configuration file created by making an HTTP request to the Connect's Restful API as seen with the command and output below:
---

$ curl -i -X POST -H "Accept:application/json" -H  "Content-Type:application/json" http://localhost:8083/connectors/ -d @register-connector.json


Check Connector Presence by making another HTTP request to Connect's Restful API:
---

$ curl -H "Accept:application/json" localhost:8083/connectors/


On redpanda
---
rpk topic consume shop-server.public.customer_addresses

On postgres container
---
psql -U postgres shop
shop=# update public.customer_addresses set state = 'Johannesburg' where id = 10;


update location_of_interest set reason = 'allergy' where last_location = 'Hawai';

CREATE STREAM test (first_name VARCHAR)
  WITH (kafka_topic='shop-server.public.customer_addresses', VALUE_FORMAT='AVRO');


% CREATE TABLE test AS
%     SELECT country,
%            count_distinct(last_name)
%     FROM customers
%     GROUP BY country;

To log into ksql: 
---
ksql http://ksqldb-server:8088


Command to format json key valut in redpanda for json format not avro
-f '%k %v\n'

example : rpk topic consume <topic-name> -f '%k %v\n'