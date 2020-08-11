##  Dynatrace OneAgent SDK Auto Instrumentation for Python

> **DISCLAIMER**: This project is not supported by Dynatrace, it is a starting point for those wanting to implement OneAgent SDK for Python with minimal code changes.

[![Downloads](https://pepy.tech/badge/autodynatrace)](https://pepy.tech/project/autodynatrace)

Dynatrace provides a [powerful SDK](https://github.com/Dynatrace/OneAgent-SDK-for-Python) that can be used to achieve code level visibility and transaction tracing for applications written in multiple languages, including python. Autodynatrace is a wrapper around the python SDK, that allows you to instrument python applications with minimal code changes.


### Usage

`pip install autodynatrace`

### Option 1 - Instrumentation without code changes

Add the environment variable `AUTOWRAPT_BOOTSTRAP=autodynatrace` to your python processes

### Option 2 - Semi-Auto Instrumentation

For most technologies, just import it in your code.

`import autodynatrace`

### Technologies supported:

- **celery**
- **concurrent.futures**
- **confluent_kafka**
- **cx_Oracle**
- **django**
- **flask**
- **grpc**
- **paramiko**
- **pika** (RabbitMQ)
- **pymongo**
- **pysnmp**
- **redis**
- **ruxit** (Dynatrace plugin framework)
- **sqlalchemy**
- **subprocess**
- **suds**
- **urllib**
- **urllib3**
- **custom annotations**

### Django

For Django, add `"autodynatrace.wrappers.django"` to `INSTALLED_APPS`

### Environment variables

* `AUTODYNATRACE_CAPTURE_HEADERS`: Default: `False`, set to `True` to capture request headers
* `AUTODYNATRACE_LOG_LEVEL`: Default `WARNING`
* `AUTODYNATRACE_FORKABLE`: Default `False`, set to `True` to [instrument forked processes](https://github.com/Dynatrace/OneAgent-SDK-for-Python#using-the-oneagent-sdk-for-python-with-forked-child-processes-only-available-on-linux)
* `AUTODYNATRACE_VIRTUAL_HOST`: Overwrite the default Virtual Host for Flaks and Django
* `AUTODYNATRACE_APPLICATION_ID`: Overwrite the default Application Name for Flask and Django
* `AUTODYNATRACE_CONTEXT_ROOT`: Overwrite the default Context Root for Flask and Django
