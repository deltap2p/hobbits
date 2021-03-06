# Conformance testing procedure

![hct](https://raw.githubusercontent.com/deltap2p/hobbits/master/test/conformance/hct.png)

### Test 1: Ping/Pong
  1) conformance app sends a ping with a random payload of bytes
  2) sample app receives the ping and returns the payload in the pong
  3) conformance app tests the payload sent vs the payload received.  
    match -> success  
    mismatch -> fail 

### Test 2: Port Test
  1) conformance app dials the sample app's tcp port
      open -> success
      closed -> fail

### Test 3:  Send/Rcv Msg 
  1) conformance app sends a message to sample app
  2) sample app receives message and returns payload in a reply message
  3) conformance app tests the payload sent vs the payload received.  
    match -> success  
    mismatch -> fail 



# Conformance testing application

This folder contains a simple go application one can use to ensure their
implementation of hobbits is able to expose a port and accept incoming TCP connections, as well as consume a hobbits message.

Usage:
```bash
$> conformance --ip <0.0.0.0> --port <0000>
```

Build:

The build requires Go 1.11 or later to be installed on the machine.

Get all dependencies:
```
go get
```
Build the program for your platform:
```
go build
```
