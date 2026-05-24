## Start docker network

    docker network create goals-network

## Starting database

    docker run --name mongodb --rm -d --network goals-network mongo

## Starting backend

    docker build -t goals-node .

    docker run --name goals-backend --rm -d --network goals-network goals-node

## Starting frontend

    docker build -t goals-react .

    docker run --name goals-frontend --rm -d --network goals-network -p 3000:3000 goals-react
