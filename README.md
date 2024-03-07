# TIG-Stack Docker Configuration

This repository contains a Dockerized implementation of the TIG stack, comprising Telegraf, InfluxDB, and Grafana, bundled together for streamlined deployment and monitoring solutions. Telegraf is a powerful agent for collecting and reporting metrics and data, feeding it into InfluxDB, a time-series database designed to handle high write and query loads efficiently. Grafana, a leading open-source analytics and visualization platform, is utilized for creating rich, interactive dashboards to visualize and analyze data stored in InfluxDB.

## Prerequisites

- Docker installed on your machine ([Install Docker](https://docs.docker.com/get-docker/))
- Docker Compose installed on your machine ([Install Docker Compose](https://docs.docker.com/compose/install/))

## Features
- Dockerized setup for easy deployment and scalability.
- Telegraf configured for various data sources and metrics collection.
- InfluxDB configured for efficient storage and retrieval of time-series data.
- Grafana configured with pre-built dashboards for visualizing key metrics. (COMING SOON)
- Customizable configurations to tailor the stack to specific use cases.
- Seamless integration with existing Docker environments for monitoring and analytics needs.

## Components

- **Telegraf**: Telegraf is an agent for collecting, processing, aggregating, and writing metrics.
- **InfluxDB**: InfluxDB is a time-series database designed to handle high write and query loads.
- **Grafana**: Grafana is an open-source platform for monitoring and observability, with a focus on providing rich metrics dashboards.

## Usage

1. Clone the repository and install the required dependencies:

```bash
$ git clone https://github.com/hetkpatel/TIG-Stack-Docker.git
$ cd TIG-Stack-Docker
```
2. Customize the configuration files as needed

3. Start the TIG stack using Docker Compose:
```bash
$ docker compose up -d
```

6. Access Grafana in your browser by visiting `http://localhost:3000`. Log in using the default credentials (username: `admin`, password: `admin`). You will be asked to change the default password.

6. Configure Grafana to connect to InfluxDB as a data source using the URL `http://influxdb:8086`.
    
    > NOTE: Use Flux as the Query Language

7. Start sending metrics data to Telegraf, which will store it in InfluxDB. You can configure Telegraf to collect metrics from various sources.

## Configuration

- Edit the port numbers, user/org details, and database config for InfluxDB in the `.env` file.

  > For `DOCKER_INFLUXDB_INIT_ADMIN_TOKEN`, run `openssl rand hex -32` in Terminal to generate a token.
- Edit the input and output plugins of Telegraf by editing the configuration file `telegraf.conf`.

## Contributing

Contributions are welcome! If you have any suggestions, improvements, or bug fixes, feel free to open an issue or create a pull request.

## License

This project is licensed under the [AGPL-3.0 License](LICENSE).


