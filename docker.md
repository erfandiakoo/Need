185.3.125.191


mkdir -p ~/.docker/cli-plugins/
curl -SL https://github.com/docker/compose/releases/download/v2.24.6/docker-compose-linux-x86_64 -o ~/.docker/cli-plugins/docker-compose

chmod +x ~/.docker/cli-plugins/docker-compose



sudo groupadd docker

sudo usermod -aG docker $USER

newgrp docker


docker run --name atra-pg -e POSTGRES_PASSWORD=YOUR_PASSWORD -d postgres


docker volume create portainer_data

docker run -d -p 8000:8000 -p 9443:9443 --name portainer --restart=always -v /var/run/docker.sock:/var/run/docker.sock -v portainer_data:/data portainer/portainer-ce:latest

docker run --name pg_db -e POSTGRES_PASSWORD=YOUR_PASSWORD -e POSTGRES_USER=atron -p 5432:5432 -v pgdata:/var/lib/postgresql/data -d postgres

docker run --rm --name tokyo -p 80:80 -d erfandiakoo/frontend:1.0

docker run --name nowrouz -e TEST_DEV=ss -p 8088:80 -d erfandiakoo/nowrouz:1.1

docker run --name berlin -e TEST_DEV=pp -p 8181:8181 -d erfandiakoo/backend:1.0

docker run -d -p 6379:6379 -v redis_data:/data --name denver redis

curl -H "Origin: https://erfandiakoo.dev" --verbose https://api.erfandiakoo.dev/v1
curl -H "Origin: http://app.erfandiakoo.dev" --verbose http://localhost:8181
