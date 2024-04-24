# Dev Depot

## Introduction

This repository houses my day-to-day local development setup so I can quickly get my required services up and running, regardless of my host's state

## Running the containers

Create your environment file specifying the necessary secrets (see [Environment variables](#environment-variables)) and run `docker compose up -d` or `docker compose -p [PROJECT_NAME] up -d`. For running one or more specific services you can run `docker compose up -d [SERVICE]`. For an overview of service names, see the `compose.yaml` file.

## Containers

- [Azurite](https://hub.docker.com/_/microsoft-azure-storage-azurite)
- [RabbitMQ](https://hub.docker.com/_/rabbitmq)
- [Redis (1)](https://hub.docker.com/_/redis)
- [Redis (2)](https://hub.docker.com/_/redis)
- [Seq](https://hub.docker.com/r/datalust/seq)
- [SFTP](https://hub.docker.com/r/atmoz/sftp)
- [SQL](https://hub.docker.com/_/microsoft-mssql-server)
- [Ubuntu Desktop](https://hub.docker.com/r/dorowu/ubuntu-desktop-lxde-vnc)

## Environment variables

Before starting any containers, create a `.env` file in the root of this repository. You can copy the `.env.example` file for reference.

You can then fill this file with the following variables for use within the compose file:
| Variable                  | Definition                                                                                   | Container                               |
| ------------------------- | -------------------------------------------------------------------------------------------- | --------------------------------------- |
| STFP_USERNAME             | A username for your sftp user                                                                | atmoz/sftp                              |
| SFTP_PASSWORD             | The password for the previously mentioned user                                               | atmoz/sftp                              |
| SFTP_ROOTFOLDER           | The root folder that the user can upload to                                                  | atmoz/sftp                              |
| SQL_SA_PASSWORD           | The password for the SQL SA user                                                             | mcr.microsoft.com/mssql/server          |
| SQL_HOSTNAME              | The hostname of your SQL container                                                           | mcr.microsoft.com/mssql/server          |
| SQL_DATA_PATH             | A volume bind path for the data folder of your SQL container (where your .mdf files will be) | mcr.microsoft.com/mssql/server          |
| SQL_LOG_PATH              | A volume bind path for the log folder of your SQL container                                  | mcr.microsoft.com/mssql/server          |
| UBUNTU_DESKTOP_FILE_SHARE | A volume bind path for sharing data between the host and the desktop container               | dorowu/ubuntu-desktop-lxde-vnc          |
| RABBITMQ_DEFAULT_USER     | The username of the RabbitMQ user                                                            | rabbitmq                                |
| RABBITMQ_DEFAULT_PASS     | The password of the RabbitMQ user                                                            | rabbitmq                                |
| AZURITE_DATA_PATH         | A volume bind path for the data folder of your Azurite container                             | mcr.microsoft.com/azure-storage/azurite |
| AZURITE_CERT_PATH         | A volume bind path for the PEM certificates for Azurite                                      | mcr.microsoft.com/azure-storage/azurite |
