qson
---

Quick JSON based key value store over http

```python
import sys
import thread

import qson

test_server = qson.Server(("0.0.0.0", 0), qson.Handler)
port = test_server.port()

thread.start_new_thread(test_server.serve_forever, tuple())

test_client = qson.client(port=port)
print test_client("key1")
print test_client("key2", {
    "test": "values"
})
print test_client("key2")
```
