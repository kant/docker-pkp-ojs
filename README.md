# Tags
**TO DO**

# Run
## Docker Compose
Create a *docker-compose.yml* file and run ```docker-compose up```.
```dockerfile
# docker-compose.yml
version: "3.6"
services:
  ojs:
    build: .
    ports: 
      - 8181:80
    environment: 
      - PKP_DATABASE_DRIVER=mysqli
      - PKP_DATABASE_HOST=mysql
      - PKP_DATABASE_USERNAME=ojs
      - PKP_DATABASE_PASSWORD=ojs
      - PKP_DATABASE_NAME=ojs
  mysql:
    image: mysql:5.7
    volumes:
      - db_data:/var/lib/mysql
    environment: 
      - MYSQL_DATABASE=ojs
      - MYSQL_USER=ojs
      - MYSQL_PASSWORD=ojs
      - MYSQL_ROOT_PASSWORD=root
  pma:
    image: phpmyadmin/phpmyadmin:4.8
    ports: 
      - 8182:80
    environment: 
      - PMA_HOST=mysql

volumes: 
  db_data:
```

## Docker Command
Run the following commands:
```bash
# to do
```