# mothrpy

![GitHub](https://img.shields.io/github/license/rs21io/mothrpy)

## Installation
`pip install mothrpy`

If you need to create a listener you need to install the optional listener
dependencies

`pip install mothrpy[listener]`

## Usage

Basic example submitting a job request

```python
from mothrpy import JobRequest

request = JobRequest(service='echo')
request.add_parameter(value='Hello MOTHR!')
result = request.run_job()
print(result)
```

Submitting a job request using `MothrClient`. This allows you to reuse the
client connection when making multiple requests.

```python
from mothrpy import JobRequest, MothrClient

client = MothrClient()
request = JobRequest(client=client, service='echo')
request.add_parameter(value='Hello MOTHR!')
result = request.run_job()
print(result)
```
