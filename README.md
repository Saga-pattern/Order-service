# Order-service

## How to build and push to docker
Clone repo
```
git clone https://github.com/Saga-pattern/Order-service.git
```

Go to the project
```
cd Order-service
```

Build project. Push image to docker hub
```
docker build -t order-service .
```
```
docker tag order-service <your-repo>:latest
```
```
docker push <your repo>:latest
```

## Event flow send and receive
