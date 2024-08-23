# Beautiful code

Experiments in writing code which can be considered a form of art.

What makes code beautiful:
- easy to understand
- has an elegance... perhaps you know it when you see it

This is all work in progress as I figure out my thoughts. Examples that seem really nice are below.

get() returns an object holding the request resposne
```python
import requests
r = requests.get('https://bbc.co.uk')
r.json()
```

SortedList which uses something like a binary tree behind the scenes
```python
from sortedcontainers import SortedList
sl = SortedList([3, 1, 2, 5, 4])
sl.pop()
```
On performance [of SortedList](https://grantjenks.com/docs/sortedcontainers/performance.html)

Caching decorator
```python
import functools as ft

@ft.lru_cache(maxsize=500)
def fib(n):
    return n if n < 2 else fib(n - 1) + fib(n - 2)
```

Stripe client
```python
from stripe import StripeClient
client = StripeClient("sk_test_...")
customers = client.customers.list()
```

Flask app
```python
from flask import Flask
app = Flask(__name__)

@app.route("/")
def hello_world():
    return "<p>Hello, World!</p>"
```

Boto3 (once your ~/.aws/credentials file is set up)
```python
import boto3
s3 = boto3.resource('s3')
for bucket in s3.buckets.all():
    print(bucket.name)
```












