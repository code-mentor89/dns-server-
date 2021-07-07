# dns-server
dns-client server communications 

Task Description:
This is a sample program to receive dns queries and forward it to a specified dns server.
The dns server is specified in the command line arguments of the executable. Sample 
command line usage: ./dns 1.1.1.1 53. It only supports specific dns query types. This also
demonstrates the use of cache to temporarily store the responses of the dns server. With
cache, the program doesn't have to request for data from the dns server for repeated requests.

Version: 1.0.0.0

Command Line Usage: ./dns [server ipv4 address] [port number]

How to Build:
Codebase is primarily written in C for standard C99 and mainly uses C standard libraries.
This uses gcc compiler and Makefile to build. To build the program, type 'make'. To delete 
the binaries (executable and object files), type 'make clean'. 

How to Test:
You can use test.sh file to test if the operation is successful. Type './test.sh' on a 
separate bash window. 

OS/Library Dependencies:
This is written in Ubuntu 18.04 Linux but can be ported to other Linux distros that support
POSIX socket libraries. Significant code rework is needed for it to work in Windows since it
uses different libraries for socket functions. 

File Structure:
cache.c/cache.h       - provides functions to implement the Cache of the DNS packets.
client.c/client.h     - provides functions to store information about the DNS query client.
listener.c/listener.h - provides functions to implement the listener for the DNS queries.
ll.c/ll.h             - provides functions to implement a linked list data structure.
log.c/log.h           - provides functions to log the events in the program.
reader.c/reader.h     - provides functions to read the contents of a DNS packet.
resolver.c/resolver.h - provides functions to store information about a connection to the
                        DNS server. 
tcp.c/tcp.h           - provides functions to read/write data to the TCP socket.
write.c/write.h       - provides functions to write the DNS structure into a DNS packet. 
