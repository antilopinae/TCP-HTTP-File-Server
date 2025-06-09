# TCP File Server
> A simple multiprocessing TCP server that implements working with files via HTTP requests.

## Individuality
Processing multiple clients using fork()  
Working over a TCP connection  

HTTP request support:  
* GET /file.txt — return the contents of the file  
* PUT /file.txt — create or overwrite a file  
* DELETE /file.txt — delete the file

Processing the Content-Length header when uploading a file  
Error handling (400, 404, 405)  

## Compilation

```
gcc -o tcpfileserver TCPServer.c passiveTCP.c passivesock.c errexit.c
```

## Launch
```
./tcpfileserver 8080
```
> (By default, the network port from /etc/services is used, if not specified.)

## Examples
```
# Saving the file
curl -X PUT --data-binary @example.txt http://localhost:8080/example.txt

# Getting the content
curl http://localhost:8080/example.txt

# Deleting a file
curl -X DELETE http://localhost:8080/example.txt

```
