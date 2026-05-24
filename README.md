## Start docker network

    docker network create goals-network

## Starting database

    docker run --name mongodb --rm -d -v data:/data/db --network goals-network -e MONGO_INITDB_ROOT_USERNAME=jason -e MONGO_INITDB_ROOT_PASSWORD=secret mongo

## Starting backend

    docker build -t goals-node .

    docker run --name goals-backend --rm -d -p 80:80 --network goals-network goals-node

## Starting frontend

    docker build -t goals-react .

    docker run --name goals-frontend --rm -d -p 3000:3000 goals-react
