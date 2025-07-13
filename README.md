# Telegraf Demo Project

Demo showcasing a data pipeline using Telegraf, InfluxDB, PostgreSQL, and Docker Compose. It processes telemetry data and stores it in multiple outputs, including InfluxDB and PostgreSQL.

## Project Structure

- **docker-compose.yml**: Defines the services and their configurations for Docker Compose.
- **input.json**: Contains sample telemetry data in JSON format.
- **telegraf-sender.conf**: Configuration for the Telegraf sender instance, which reads telemetry data and forwards it.
- **telegraf-receiver.conf**: Configuration for the Telegraf receiver instance, which listens for incoming telemetry data and writes it to outputs.
- **README.md**: Documentation for the project.

## Services

### InfluxDB
- Stores telemetry data in a time-series database.
- Accessible on port `8086`.

### PostgreSQL
- Stores telemetry data in a relational database.
- Accessible on port `5432`.

### Telegraf Sender
- Reads telemetry data from `input.json`.
- Sends data to the Telegraf Receiver via TCP.

### Telegraf Receiver
- Listens for incoming telemetry data on port `8080`.
- Writes data to InfluxDB, PostgreSQL, and stdout.

### pgAdmin
- Web-based administration tool for PostgreSQL.
- Accessible on port `80`.


### Useful Links
- [Telegraf Documentation](https://docs.influxdata.com/telegraf/v1.28/)
- [Telegraf Repo](http://github.com/influxdata/telegraf)

Each plugin in Telegraf has its own documentation, which can be found in the plugin readme from the repo.

Note: Telegraf will continuously read from `input.json` and send data to the receiver. It has a flag to be run in a one-shot mode.