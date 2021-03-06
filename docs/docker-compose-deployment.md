# Deploying Alfresco Content Services using Docker Compose

Use this information to quickly start up Alfresco Content Services (ACS) using Docker Compose.

## Prerequisites

To deploy Alfresco Content Services using _docker-compose_, you'll need to install the following software:

| Component      | Installation Guide |
| ---------------| ------------------ |
| Docker         | https://docs.docker.com/ |
| Docker Compose | https://docs.docker.com/compose/install/ |

## Structure

![Docker Compose Deployment Components](./diagrams/docker-compose/docker-compose-components.png)

## Deploying Alfresco Content Services
1. Clone this repository or download a single file - [docker-compose](../docker-compose/docker-compose.yml).
2. Navigate to the folder where the _docker-compose.yml_ file is located.
3. Run ```docker-compose up```
4. Open the following URLs in your browser to check that everything starts up:
* http://<machine_ip>:8082/alfresco
* http://<machine_ip>:8080/share
* http://<machine_ip>:8083/solr

**Note:**
* Make sure ports 5432, 8080, 8082, and 8083 are open. These are defined in the _docker-compose.yml_ file.
* If Docker is running on your local machine, the IP address will be just _localhost_.
* If you're using the [Docker Toolbox](https://docs.docker.com/toolbox/toolbox_install_windows), run the following command to find the IP address:
```bash
docker-machine ip
```
* If you run ```docker-compose up``` after deleting a previous Docker Compose cluster, then replace step 3 with the following command:
```bash
docker-compose down && docker-compose build --no-cache && docker-compose up
```
