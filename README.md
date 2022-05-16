# Strapi Crash Course 1

Use node v16 as v17, v18, ... failed.

```bash
npx create-strapi-app@latest myproject --quickstart
npm i pg knex # strapi-connector-bookshelf # not needed in 4.0
# ^c # to stop server before filling out details
# create Dockerfile and .dockerignore file
docker build -t strapi-4-cc-1:latest .
docker run -d -p 1337:1337 strapi-4-cc-1
# setup ./config/database and ./.env
# docker-compose installation instructions below
docker compose up -d postgresDB && npm run develop # local dev
# or
docker compose up -d # full containerized
```

## docker-compose installation

From:
https://docs.docker.com/compose/install/#install-the-binary-manually

```bash
 DOCKER_CONFIG=${DOCKER_CONFIG:-$HOME/.docker}
 mkdir -p $DOCKER_CONFIG/cli-plugins
 curl -SL https://github.com/docker/compose/releases/download/v2.5.0/docker-compose-linux-x86_64 -o $DOCKER_CONFIG/cli-plugins/docker-compose
chmod +x $DOCKER_CONFIG/cli-plugins/docker-compose
docker compose version
```

## Code History

The code in this repository is base on the following content:

- https://blog.dehlin.dev/docker-with-strapi-v4
- https://youtu.be/vcopLqUq594

## Code Help

Some links I found on using Strapi with K8s.

- https://strapi.io/blog/deploying-and-scaling-the-official-strapi-demo-app-foodadvisor-with-kubernetes
- https://developers.redhat.com/blog/2021/04/09/containerize-and-deploy-strapi-applications-on-kubernetes-and-red-hat-openshift#
- https://stackoverflow.com/questions/71374273/getting-error-when-i-run-strapi-in-kubernetes
