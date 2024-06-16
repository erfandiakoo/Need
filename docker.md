mkdir -p ~/.docker/cli-plugins/

curl -SL https://github.com/docker/compose/releases/download/v2.24.6/docker-compose-linux-x86_64 -o ~/.docker/cli-plugins/docker-compose

chmod +x ~/.docker/cli-plugins/docker-compose

newgrp docker

sudo usermod -aG docker $USER

sudo groupadd docker

docker run --name "NAME" -e POSTGRES_PASSWORD=YOUR_PASSWORD -d postgres

docker volume create portainer_data

docker run -d -p 8000:8000 -p 9443:9443 --name portainer --restart=always -v /var/run/docker.sock:/var/run/docker.sock -v portainer_data:/data portainer/portainer-ce:latest

docker run --name "NAME" -e POSTGRES_PASSWORD=YOUR_PASSWORD -e POSTGRES_USER=atron -p 5432:5432 -v pgdata:/var/lib/postgresql/data -d postgres

docker run --rm --name "NAME" -p 80:80 -d erfandiakoo/frontend:1.0

docker run --name nowrouz -e TEST_DEV=ss -p 80:80 -d erfandiakoo/nowrouz:1.1

docker run --name berlin -e TEST_DEV=pp -p 80:80 -d erfandiakoo/backend:1.0

docker run -d -p 6379:6379 -v redis_data:/data --name "NAME" redis

docker cp foo.txt container_id:/foo.txt

docker cp container_id:/foo.txt foo.txt


docker run -e "ACCEPT_EULA=Y" -e "MSSQL_SA_PASSWORD=yourStrong(!)Password" -p 1433:1433 -d mcr.microsoft.com/mssql/server:2019-latest

docker run -e 'ACCEPT_EULA=Y' -e 'SA_PASSWORD=YourPassword123' \
-p 1433:1433 --name sqlserver_container \
-v sqlserver_data:/var/opt/mssql \
-d mcr.microsoft.com/mssql/server


psql -U "username" -W -d "database" -f "filepath"
