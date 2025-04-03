# `pymemcache`

* Good performance
* Pure Python code
* Handles exceptions
* Implements serialization (pickling)

`pip install pymemcache`

```
from pymemcache.client.base import Client
client = Client(('127.0.0.1', 11211))
client.set('key', b'value', expire=3600)
value = client.get('key')
```

# `pylibmc`

* Wraps a C library for maximum performance
* Full support for advanced features
* Supports the optimized binary protocol

`pip install pylibmc`

```
import pylibmc
client = pylibmc.Client(["127.0.0.1:11211"], binary=True)
client.set('key', 'value', time=3600)
value = client.get('key')
```