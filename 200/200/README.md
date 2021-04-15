# 200 - Use a Client to Interact with a Network-Accessible Service

A Ballerina client is a component, which interacts with a network-accessible service. It aggregates one or more actions that can be executed on the network-accessible service and accepts configuration parameters related to the network-accessible service.

There are two kinds of clients in Ballerina, inbound (or ingress) and outbound (or egress) clients. An outbound client object can be used to send messages to a network service.

Having said that, let’s see how you can use a Ballerina client to invoke the Hello World service.

First, you need to create the client with the relevant endpoint URL as follows. We will use a Ballerina program with a ```main``` function, which will perform the invocation.

***Note***: returning ```error?``` allows you to use the ```check``` keyword to avoid handling errors explicitly. This is only done to keep the code simple. However, in real production code, you may have to handle those errors explicitly.

