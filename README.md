# grafana-compose


The idea of this compose file is to allow easy monitoring of the lift container logs when running locally

## Prerequisites
All that is needed to see the logs in grafana is to install the loki docker plugin

`docker plugin install grafana/loki-docker-driver:latest --alias loki --grant-all-permissions`

or for ARM (M1?)
`docker plugin install grafana/loki-docker-driver:arm-v7 --alias loki --grant-all-permissions`

to confirm the installation:
`docker plugin ls`

To Run: `docker-compose up`

Log in to Grafana: `localhost:4000`
Initial login credentials are:
username: `admin`, password: `admin`

## Configuration
Unfortunately out of the box I have not found a way to pre-configure data sources without commit the database, so these manual steps are required to start consuming logs

- Configuration -> Datasources
- Add Datasource -> Loki
- In the url add `http://loki:3100`
- Add Datasource -> Jaeger
- In the url add `http://jaeger:16686`

Go to the explore section to start seeing logs .... 