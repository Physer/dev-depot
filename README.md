# Dev Depot
## Introduction

This repository houses my day-to-day local development setup so I can quickly get my required services up and running, regardless of my host's state

## Running the containers
Create your environment file specifying the necessary secrets (see [Environment variables](#environment-variables)) and run `docker-compose up -d` or `docker-compose -p stack-name up -d`.

## Containers
- [Azurite](https://hub.docker.com/_/microsoft-azure-storage-azurite)
- [Redis (1)](https://hub.docker.com/_/redis)
- [Redis (2)](https://hub.docker.com/_/redis)
- [Seq](https://hub.docker.com/r/datalust/seq)
- [SFTP](https://hub.docker.com/r/atmoz/sftp)
- [SQL](https://hub.docker.com/_/microsoft-mssql-server)

## Environment variables
In order to make this compose file generic and accessible, you can create a `.env` file in the folder where your compose file is located.

You can then fill this file with the following variables for use within the compose file:
| Variable                     | Definition                                                                                   | Container                      |
|------------------------------|----------------------------------------------------------------------------------------------|--------------------------------|
| STFP_USERNAME                | A username for your sftp user                                                                | atmoz/sftp                     |
| SFTP_PASSWORD                | The password for the previously mentioned user                                               | atmoz/sftp                     |
| SFTP_ROOTFOLDER              | The root folder that the user can upload to                                                  | atmoz/sftp                     |
| SQL_SA_PASSWORD              | The password for the SQL SA user                                                             | mcr.microsoft.com/mssql/server |
| SQL_HOSTNAME                 | The hostname of your SQL container                                                           | mcr.microsoft.com/mssql/server |
| SQL_DATA_PATH                | A volume bind path for the data folder of your SQL container (where your .mdf files will be) | mcr.microsoft.com/mssql/server |
| SQL_LOG_PATH                 | A volume bind path for the log folder of your SQL container                                  | mcr.microsoft.com/mssql/server |
| UBUNTU_DESKTOP_FILE_SHARE    | A volume bind path for sharing data between the host and the desktop container               | dorowu/ubuntu-desktop-lxde-vnc |

