# 200 - Use a Client to Interact with a Network-Accessible Service

A Ballerina client is a component, which interacts with a network-accessible service. It aggregates one or more actions that can be executed on the network-accessible service and accepts configuration parameters related to the network-accessible service.

There are two kinds of clients in Ballerina, inbound (or ingress) and outbound (or egress) clients. An outbound client object can be used to send messages to a network service.

Having said that, let’s see how you can use a Ballerina client to invoke the Hello World service.

First, you need to create the client with the relevant endpoint URL as follows. We will use a Ballerina program with a ```main``` function, which will perform the invocation.

***Note***: returning ```error?``` allows you to use the ```check``` keyword to avoid handling errors explicitly. This is only done to keep the code simple. However, in real production code, you may have to handle those errors explicitly.

```http:Client helloClient = new("http://localhost:9090/hello");```

As the next step, add the below code to do a ```GET``` request to the Hello World service.

```http:Response helloResp = check helloClient->get("/sayHello");```

The remote call would return an ```http:Response``` if successful, or an ```error``` on failure. If successful, attempt retrieving the payload as a ```string``` and print the payload.

```io:println(check helloResp.getTextPayload());```

The complete source code should look similar to the following:

```
import ballerina/http;
import ballerina/io;

public function main() returns @tainted error? {
    http:Client helloClient = new("http://localhost:9090/hello");
    http:Response helloResp = check helloClient->get("/sayHello");
    io:println(check helloResp.getTextPayload());
}
```
hello_client.bal

Make sure the service is up and running.

Now, you can run the ```.bal``` file containing the ```main``` function that invokes the service.

```$ ballerina run hello_client.bal```

This would produce the following output.

```Hello Ballerina!```

Similarly, you can use a Ballerina HTTP client to interact with any HTTP service.

Now, let’s look at a simple HTTP client that retrieves sunrise/sunset time details for Colombo.

Create a client with the relevant endpoint URL as follows.

```http:Client sunriseApi = new("http://api.sunrise-sunset.org");```

As the next step, add the below code to do a ```GET``` request to the sunrise-sunset backend.

```http:Response sunriseResp = check sunriseApi->get("/json?lat=6.9349969&lng=79.8538463");```

Now, add the below code snippet to retrieve the payload and print it.

```
json sunrisePayload = check sunriseResp.getJsonPayload();
io:println(sunrisePayload);
```

The complete source code should look similar to the following:

```
import ballerina/http;
import ballerina/io;

public function main() returns @tainted error? {
    http:Client sunriseApi = new("http://api.sunrise-sunset.org");
    http:Response sunriseResp = check sunriseApi->get("/json?lat=6.9349969&lng=79.8538463");
    json sunrisePayload = check sunriseResp.getJsonPayload();
    io:println(sunrisePayload);
}
```
sunrise_client.bal

Now, you can invoke the service using this client by running the following command.

```$ ballerina run sunrise_client.bal```

This should print out the sunrise/sunset details.
