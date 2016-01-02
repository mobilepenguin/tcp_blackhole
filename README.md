# TCP Blackhole

## Summary

TCP Blackhole is a server that can discard data it receives, print it to standard out, or echo it back to the client as raw data or as an HTTP 200 OK response.

## Description

Blackhole will establish TCP connection with a requesting client and then read and discard until the connection is closed.
If the echo option is turned on, the Blackhole server will send back any information it receives. With the debug option
on, it will print out any data received to standard output. With the HTTP option it will respond as an HTTP server
with a 200 OK. HTTP option can be used in combination with the echo option. In that case the data received will be returned
as the contents of the HTTP OK response. Blackhole is a useful server for testing and capturing packets from a client.
Written with Python.

## Installation

	$ pip install tcp_blackhole

## Usage

	$ blackhole <host> <port> [--echo] [--debug] [--http]


## Including in other Python scripts

```
from tcp_blackhole import TcpBlackhole
blackhole = TcpBlackhole(
        host='localhost',
        port=9999,
        echoFlag=True,
        debugFlag=True,
        httpFlag=True)
blackhole.start()
```

## Contact

nanodano@devdungeon.com

## Changelog

* 0.3.3 - Fixed broken tuple argument for thread. Updated setup.py to install .bat always
* 0.3.2 - Added blackhole.bat for convenience in Windows version. setup.py updated to only install it on nt systems. 
* 0.3.1 - Fixed import statement in readme and formatting of the changelog section. Removed unused running variable.
* 0.3.0 - Add --http option to return data as an HTTP 200 OK. Can be used in combination with echo feature.
* 0.2.0 - Added --echo feature to send data back to client and --debug feature to output to STDOUT
* 0.1.0 - Added basic discard feature


