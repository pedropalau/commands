# Docker

[Docker](https://www.docker.com/) is a computer program that performs operating-system-level virtualization also known as containerization.

## Contents

- [Requirements](#requirements)
- [Installation](#installation)
- [Commands](#commands)
- [Throubleshooting](#throubleshooting)
- [Resources](#resources)

## Requirements

TBD

## Installation

TBD

## Commands

To show only running containers:

```
$ docker container ls
```

To show all containers:

```
$ docker container ls -a
```

To show the latest created container (includes all states):

```
$ docker ps -l
```

To show n last created containers (includes all states):

```
$ docker ps -n=-1
```

To display total file sizes:

```
$ docker ps -s
```

Clean all running containers:

```
$ docker rm $(docker ps -aq)
```

## Throubleshooting

1. Solving error: `bind: address already in use`

   Check the process using the address or `PORT` with the command:
  
   ```
   $ sudo netstat -pna | grep <PORT>
   ```

## Resources

### OpenSource
- [Projects](https://www.docker.com/community/open-source)
- [GitHub Enterprise Page](https://github.com/docker)

### Community
- [Docker Community](https://www.docker.com/docker-community)
- [Events](https://events.docker.com/)

### Tools
- [Documentation](https://docs.docker.com/)
- [Engineering Blog](https://engineering.docker.com/)
