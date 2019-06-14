# Operating Systems

## Contents

- [Booting](https://github.com/peterpalau/commands/tree/master/operating-systems/booting)
- [General purpose commands](#general-purpose-commands)
  - [Killing process](#killing-process)

## General purpose 

### Killing process

1. Kill a process running on a specific port:

```
$ sudo kill $(sudo lsof -t -i:<PORT>)
```
