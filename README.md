# grafana-compose

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