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
### Order created
After receiving the request to create an order, the order will be saved to the database and send an event object to the "create-order" topic of kafka. Status order is ORDER_CREATED

### Approve order
Order service will receive event from kafka "approve-order" topic. Then order will be updated status to ORDER_COMPLETED.

### Reject order
Order service will receive event from kafka "reject-order" topic. Then order status will be updated to ORDER_CANCELLED
