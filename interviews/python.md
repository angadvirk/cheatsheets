# Python

## Performing an HTTP Request in Python

First, install `requests` library:
```shell
pip install requests
```

Then:
```python
import requests

# GET request
response = requests.get('https://pythonexamples.org/python-basic-examples/')

# convert json response to Python dictionary
response_dict = response.json()
```

More features of Python `requests` library can be found here: https://pythonexamples.org/python-requests-http-get/