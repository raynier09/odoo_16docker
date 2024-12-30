## Odoo v15 using Docker and Docker Compose


### Prerequisite

Installation 
* Install Docker-CE
* Docker-compose

#

> Need to create a directory first [addons/, enterprise/]

```
mkdir addons

mkdir enterprise
```
### Start the command
```
docker-compose up 
```

### Other docker command

```
docker-compose up -d - Starts the containers in the background.
docker-compose up --build - Build all containers if any changes made in config and yml file
docker-compose restart - Restarts all the services.
docker-compose down - Destroy all containers
docker-compose stop - Stops all the service
```

### Useful command 

```
docker exec -it <container name> <command> 
```

> Navigate to command-line utility of the container
```
docker exec -it odoo_15 /bin/bash 
```

> Update the POS BIR Module
```
docker-compose restart web

docker exec -it odoo_15 odoo -d <db_name> --db_host db -r odoo15 -w odoo15 -u pos_bir_cpti --stop-after-init
```

> Update all Odoo Module
```
docker-compose restart web

docker exec -it odoo_15 odoo -d <db_name> --db_host db -r odoo15 -w odoo15 -u all --stop-after-init
```

> Use the odoo shell
```

docker exec -it odoo_15 odoo shell -d <db_name> --db_host db -r odoo15 -w odoo15 
```

