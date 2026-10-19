
## Messaging Queues

**Problem:** When 2 systems need to talk to eachother, we create an API where receiving system has to be available and this is a synchronous process.
Lets say I shouldnt be worried if the client I am sending to is available or not we can create a asynchronous process to send messages
not worry about delivering to the client. Think like you are placing an order of pizza by calling if noone receives the call you cannot place the order
If you are able to send a message or place online and you receive an acknowledgement you can be sure instead of calling again until they lift.

This is when messaging queue can be used.
* acts as a buffer between producer and consumer
* decouples services to operate independently
* improves scalability
* Enchances fault tolerance by storing messages until they are processed

