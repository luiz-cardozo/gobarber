# gobarber

This application uses postgres to store all the data except notifications that will be stored using mongo and mail queue that uses redis

## Project Setup

First of all install all dependencies using

```
yarn
```

### Docker images

Once you've installed docker run

```
docker run --name gobarberdb -e POSTGRES_PASSWORD=docker -p 5432:5432 -d postgres
docker run --name gobarbermongo -p 27017:27017 -d -t mongo
docker run --name gobarberredis -p 6379:6379 -d -t redis:alpine
```

### Database

```
npx sequelize db:migrate
```

### Env

There's an .env.example file, please add your own enviromental variables in order to properly run the application

### Basic scripts to run the application

To run the main application

```
yarn dev
```

and to start the queue run

```
yarn queue
```
