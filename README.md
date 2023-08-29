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
Order service will receive event from kafka's "approve-order" topic when it has checked stock and paid successfully. Then order will be updated status to ORDER_COMPLETED.

### Reject order
Order service will receive event from topic "reject-order" when stock faild or payment error. Then order status will be updated to ORDER_CANCELLED
