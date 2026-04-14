Changelog
=========

0.1.7 (2026-04-15)
------------------

- switched to underscores in project name
- `srh-listen` now uses a global object to retain the redis objects, avoiding `ValueError: I/O operation on closed file.`
- `srh-listen` now has the parameter `-t/--timeout` for the thread timeout, default is now 0.01 instead of 0.001 to
  reduce CPU load


0.1.6 (2024-02-27)
------------------

- using `srh-` prefix in the argparser's `prog` parameter now
- added `srh-ping` command to check server availability


0.1.5 (2023-07-10)
------------------

- fixed password support when accessing environment variable


0.1.4 (2023-07-07)
------------------

- fixed password support


0.1.3 (2023-07-07)
------------------

- added support for supplying a password for connecting to the Redis server (`--password` or `--password_env`)


0.1.2 (2021-10-01)
------------------

- `listen.py` now supports output in a directory


0.1.1 (2021-09-22)
------------------

- `broadcast.py` now supports reading binary files and just using simple strings


0.1.0 (2021-09-14)
------------------

- initial release

