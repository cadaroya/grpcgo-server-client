# Sample Go GRPC server and client for K8s

This code is for testing server to client connection in k8s.


## Setup

Build client:
```
cd greeter_client
GOOS=linux GOARCH=amd64 go build .
```

Build server:
```
cd greeter_server
GOOS=linux GOARCH=amd64 go build .
```

Build client and server using this command: 
```
docker build -t <image-name>:latest .
```

Push your image to some registry, then take note of the image-name. Replace <image-name-here> on server.yaml


Deploy to k8s:
```
cd deploy
kubectl apply -f server.yaml
```

