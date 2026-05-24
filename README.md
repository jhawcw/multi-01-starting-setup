## Start docker network

    docker network create goals-network

## Starting database

    docker run --name mongodb --rm -d -p 27017:27017 mongo

## Starting backend

    docker build -t goals-node .

    docker run --name goals-backend --rm -d -p 80:80 goals-node

## Starting frontend

    docker build -t goals-react .

    docker run --name goals-frontend --rm -d -p 3000:3000 goals-react
