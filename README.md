# TCP Blackhole

## Summary
Run a TCP server on a specific port to act like a TCP /dev/null. Optionally runs as an echo server.

## Description

Blackhole will establish TCP connection with a requesting client and then read and discard until the connection is closed.
If the echo option is turned on, the Blackhole server will send back any information it receives. Blackhole is a useful
server for testing and capturing packets from a client. Written with Python 3.

## Installation

pip install tcp_blackhole

## Usage

```
blackhole <host> <port> [--echo]
```

## Including in other Python scripts

```
import tcp_blackhole
blackhole = tcp_blackhole.TcpBlackhole(host='localhost', port=9876, echo=False)
blackhole.start()
```

# Contact

nanodano@devdungeon.com




