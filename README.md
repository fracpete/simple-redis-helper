# redis_helper
Little command-line library to send/receive data to/from a Redis backend.

## Installation

*redis_helper* is a Python 3 library, which you can install in virtual
environments as follows:

```commandline
pip install redis_helper
```

## Utilities

### Load

Uploads a file into the Redis backend.

```
usage: rh-load [-h] [-H HOST] [-p PORT] [-d DB] -k KEY -f FILE

Loads a file into Redis under the specified key.

optional arguments:
  -h, --help            show this help message and exit
  -H HOST, --host HOST  The redis server to connect to (default: localhost)
  -p PORT, --port PORT  The port the redis server is listening on (default:
                        6379)
  -d DB, --database DB  The redis database to use (default: 0)
  -k KEY, --key KEY     The key to store the file content under (default:
                        None)
  -f FILE, --file FILE  The file to load into Redis (default: None)
```

### Save

Saves the content of a key in the Redis backend to a file.

```
usage: rh-save [-h] [-H HOST] [-p PORT] [-d DB] -k KEY [-f FILE] [-s]

Saves the content from a Redis key in the specified file.

optional arguments:
  -h, --help            show this help message and exit
  -H HOST, --host HOST  The redis server to connect to (default: localhost)
  -p PORT, --port PORT  The port the redis server is listening on (default:
                        6379)
  -d DB, --database DB  The redis database to use (default: 0)
  -k KEY, --key KEY     The key to retrieve (default: None)
  -f FILE, --file FILE  The file to save the content in. Outputs the content
                        to stdout if not provided. (default: None)
  -s, --convert_to_string
                        Whether to convert the retrieved bytes to string
                        (default: False)
```

### Broadcast

Broadcasts the content of the specified on a Redis channel.

```
usage: rh-broadcast [-h] [-H HOST] [-p PORT] [-d DB] -c CHANNEL -f FILE

Loads a file and broadcasts its content to the specified Redis channel.

optional arguments:
  -h, --help            show this help message and exit
  -H HOST, --host HOST  The redis server to connect to (default: localhost)
  -p PORT, --port PORT  The port the redis server is listening on (default:
                        6379)
  -d DB, --database DB  The redis database to use (default: 0)
  -c CHANNEL, --channel CHANNEL
                        The channel to broadcast the content on (default:
                        None)
  -f FILE, --file FILE  The file to load into Redis (default: None)
```

### Listen

Listens to messages being broadcast on a Redis channel.

```
usage: rh-listen [-h] [-H HOST] [-p PORT] [-d DB] -c CHANNEL

Listens to the specified channel for messages to come through and outputs them
on stdout.

optional arguments:
  -h, --help            show this help message and exit
  -H HOST, --host HOST  The redis server to connect to (default: localhost)
  -p PORT, --port PORT  The port the redis server is listening on (default:
                        6379)
  -d DB, --database DB  The redis database to use (default: 0)
  -c CHANNEL, --channel CHANNEL
                        The channel to broadcast the content on (default:
                        None)
```
