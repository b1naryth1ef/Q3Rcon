# Q3Rcon

## About
Q3Rcon is a Python API to interface with Quake 3 servers over their built-in protocol titled RCON, or Remote Console.

## Example

```
from rcon import RCON

r = RCON("myserver.com", password="myrconpassword", port=27960)

r.rcon("fraglimit 9000") #Set the fraglimit to 9000
print r.rcon("status") #Get the status message
```

## Special Methods
- `RCON().getCvar(name)` will retrieve a cvar value from the server (Tested on ioUrT, not on any other Q3 system.)

## Notes, Limitations
- Q3Rcon is 100% thread and instance safe. (You can thread it, or use multiple instances of it at a time)
- Q3Rcon uses non-blocking network IO. The upside is your entire program wont block, the downside is you may not always recieve data from the server


## Benchmarks
Q3Rcon when run from the plain command-line runs basic benchmarks on a localhost server to test the command throughput
```
$ python rcon.py
elapsed time to send 100 cmds was 52 secs
$ python rcon.py
elapsed time to send 10 cmds was 4 secs
```


## Authors/Credits
- [spekode](http://github.com/spekode) Wrote most of the starting code, thread-safety, general stuff
- [b1naryth1ef](http://github.com/b1naryth1ef) Updates, formatting, maintaince, release