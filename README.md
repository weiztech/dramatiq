# dramatiq

[![Build Status](https://travis-ci.org/Bogdanp/dramatiq.svg?branch=master)](https://travis-ci.org/Bogdanp/dramatiq)
[![Test Coverage](https://codeclimate.com/github/Bogdanp/dramatiq/badges/coverage.svg)](https://codeclimate.com/github/Bogdanp/dramatiq/coverage)
[![Code Climate](https://codeclimate.com/github/Bogdanp/dramatiq/badges/gpa.svg)](https://codeclimate.com/github/Bogdanp/dramatiq)
[![PyPI version](https://badge.fury.io/py/dramatiq.svg)](https://badge.fury.io/py/dramatiq)
[![Documentation](https://img.shields.io/badge/doc-latest-brightgreen.svg)](http://dramatiq.defn.io)

**dramatiq** is a distributed task processing library for Python with
a focus on simplicity, reliability and performance.

Here's what it looks like:

``` python
import dramatiq

@dramatiq.actor
def send_welcome_email(user_id):
  user = User.get_by_id(user_id)
  mailer = Mailer.get_mailer()
  mailer.send(to=user.email, subject="Welcome", body="Welcome to our website!")

# ... somewhere in your signup process
send_welcome_email.send(new_user.id)
```

## Installation

If you want to use it with [RabbitMQ][rabbit]

    pip install -U dramatiq[rabbitmq, watch]

or if you want to use it with [Redis][redis]

    pip install -U dramatiq[redis, watch]

## Documentation

Documentation is available at http://dramatiq.defn.io.

## License

dramatiq is licensed under the AGPL.  Please see [LICENSE][license]
for licensing details.

Commercial licensing options are available [upon request][mailto].


[license]: https://github.com/Bogdanp/dramatiq/blob/master/LICENSE
[mailto]: mailto:bogdan@defn.io
[rabbit]: https://www.rabbitmq.com/
[redis]: https://redis.io
