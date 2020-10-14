# Python AMCP Client Library
> v0.2.0


## Introduction
_TBD_


## Installation
```shell
pip install amcp_pylib
```


## Usage examples
Below you can see various usage examples.

### Connecting to server

```python
from amcp_pylib.core import Client

client = Client()
client.connect("caspar-server.local", 6969)  # defaults to 127.0.0.1, 5250
```

Built-in support for `asyncio` module:
```python
import asyncio
from amcp_pylib.core import ClientAsync

client = ClientAsync()
asyncio.new_event_loop().run_until_complete(client.connect("caspar-server.local", 6969))
```

### Sending commands

```python
from amcp_pylib.core import Client
from amcp_pylib.module.query import VERSION, BYE

client = Client()
client.connect()

response = client.send(VERSION(component="server"))
print(response)

response = client.send(BYE())
print(response)
```

```shell
2.0.7.e9fc25a Stable (201 - VERSION)
SERVER SENT NO RESPONSE (0 - EMPTY)
```

All supported protocol commands are listed and documented on CasparCG's [wiki pages](https://github.com/CasparCG/help/wiki/AMCP-Protocol#table-of-contents).
