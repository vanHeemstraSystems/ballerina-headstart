# 100 - Write a Service, Run It, and Invoke It

Write a simple Hello World service in a file with the ```.bal``` extension.

```
import ballerina/http;
import ballerina/io;

# A service representing a network-accessible API
# bound to port `9090`.
service /hello on new http:Listener(9090) {

    # A resource representing an invokable API method
    # accessible at `/hello/sayHello`.
    #
    # + caller - the client invoking this resource
    # + request - the inbound request
    resource function sayHello(http:Caller caller, http:Request request) {

        // Sends a response back to the caller.
        error? result = caller->respond("Hello Ballerina!");
        if (result is error) {
            io:println("Error in responding: ", result);
        }
    }
}
```
examples/hello_world.bal

Now, you can run the service by running the following command.

```$ bal run hello_world.bal```

You get the following output.

```[ballerina/http] started HTTP/WS listener 0.0.0.0:9090```

This means your service is up and running. You can invoke the service using an HTTP client. In this case, we use cURL.

```$ curl http://localhost:9090/hello/sayHello```

***Tip***: If you do not have cURL installed, you can download it from [https://curl.haxx.se/download.html](https://curl.haxx.se/download.html).

You get the following response.

```Hello Ballerina!```

Alternatively, you can use a Ballerina HTTP client to invoke the service.
