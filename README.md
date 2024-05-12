# Contenedores de base de datos
Cuando necesitas tener diferentes motores de base de datos SQL y NOSQL en un mismo servidor, debes instalar docker. Esto te ayudara a implementar cada servicio de forma ordenada y aislada, y con los requerimientos necesarios para cada servicio.
La implementación de estos servicios en docker son:
- MsSQL
- PostgreSQL
- MariaDB
- DynamoDB
### MSSQL
Para este caso se esta usando la imagen de SQL Server 2017 Development. Para descargar la imagen usa el siguiente comando:
```bash
docker pull mcr.microsoft.com/mssql/server:2017-latest
```
Para desplegar el servicio de MS SQL Server ingresa a la carpeta `/mssql` y ejecuta el siguente comando:
```bash
docker-compose up -d
```
Los datos se almacenan en volumen para la persistencia de datos.
```docker
volumes:
  sqldata:
  sqllog:
```
Tambien que habilita un volumen para compartir los backups
```docker
./backup:/var/opt/mssql/backup
```
### PostgreSQL
Para este caso se esta usando la imagen de PostgreSQL 16.3. Para descargar la imagen usa el siguiente comando:
```bash
docker pull postgres
```
Para desplegar el servicio de PostgreSQL ingresa a la carpeta `/postgresql` y ejecuta el siguente comando:
```bash
docker-compose up -d
```
Los datos se almacenan en volumen para la persistencia de datos.
```docker
volumes:
  pgdata:
```
Tambien que habilita un volumen para compartir los backups
```docker
./backup:/backup
```
### MariaDB
Para este caso se esta usando la imagen de MariaDB 11.3. Para descargar la imagen usa el siguiente comando:
```bash
docker pull mariadb
```
Para desplegar el servicio de MariaDB ingresa a la carpeta `/mariadb` y ejecuta el siguente comando:
```bash
docker-compose up -d
```
Los datos se almacenan en volumen para la persistencia de datos.
```docker
volumes:
  mysqldata:
```
Tambien que habilita un volumen para compartir los backups
```docker
./backup:/backup
```
### DynamoDB
Para este caso se esta usando la imagen de DynamoDB. Para descargar la imagen usa el siguiente comando:
```bash
docker pull amazon/dynamodb-local:latest
```
Para desplegar el servicio de DynamoDB ingresa a la carpeta `/dynamodb` y ejecuta el siguente comando:
```bash
docker-compose up -d
```
Los datos se almacenan en volumen para la persistencia de datos.
```docker
volumes:
  dynamodbdata:
```
Tambien que habilita un volumen para compartir los backups
```docker
./backup:/backup
```