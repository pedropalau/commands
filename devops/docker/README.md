# Docker

[Docker](https://www.docker.com/) is a computer program that performs operating-system-level virtualization also known as containerization.

## Contents

- [Requirements](#requirements)
- [Installation](#installation)
- [Commands](#commands)
- [Throubleshooting](#throubleshooting)
- [Resources](#resources)

## Requirements

First, update your existing list of packages:

```
$ sudo apt update
```

Next, install a few prerequisite packages which let apt use packages over HTTPS:

```
$ sudo apt install apt-transport-https ca-certificates curl software-properties-common
```

## Installation

Installation process for Docker Community Edition (CE) on Ubuntu 18.04.

Taken from [https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-ubuntu-18-04](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-ubuntu-18-04).

### Step 1 — Installing Docker

Add the GPG key for the official Docker repository to your system:

```
$ curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
```

Add the Docker repository to APT sources:

```
$ sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu bionic stable"
```

Next, update the package database with the Docker packages from the newly added repo:

```
$ sudo apt update
```

Make sure you are about to install from the Docker repo instead of the default Ubuntu repo:

```
$ apt-cache policy docker-ce
```

You'll see output like this, although the version number for Docker may be different:

```
docker-ce:
  Installed: (none)
  Candidate: 18.03.1~ce~3-0~ubuntu
  Version table:
     18.03.1~ce~3-0~ubuntu 500
        500 https://download.docker.com/linux/ubuntu bionic/stable amd64 Packages
```

Notice that `docker-ce` is not installed, but the candidate for installation is from the Docker repository for Ubuntu 18.04 (`bionic`).

Finally, install Docker:

```
$ sudo apt install docker-ce
```

Docker should now be installed, the daemon started, and the process enabled to start on boot. Check that it's running:

```
$ sudo systemctl status docker
```

The output should be similar to the following, showing that the service is active and running:

```
● docker.service - Docker Application Container Engine
   Loaded: loaded (/lib/systemd/system/docker.service; enabled; vendor preset: enabled)
   Active: active (running) since Thu 2018-07-05 15:08:39 UTC; 2min 55s ago
     Docs: https://docs.docker.com
 Main PID: 10096 (dockerd)
    Tasks: 16
   CGroup: /system.slice/docker.service
           ├─10096 /usr/bin/dockerd -H fd://
           └─10113 docker-containerd --config /var/run/docker/containerd/containerd.toml
```

Installing Docker now gives you not just the Docker service (daemon) but also the `docker` command line utility, or the Docker client.

### Step 2 — Executing the Docker Command Without Sudo

By default, the `docker` command can only be run the __root__ user or by a user in the __docker__ group, which is automatically created during Docker's installation process. If you attempt to run the docker command without prefixing it with `sudo` or without being in the __docker__ group, you'll get an output like this:

```
docker: Cannot connect to the Docker daemon. Is the docker daemon running on this host?.
See 'docker run --help'.
```

If you want to avoid typing `sudo` whenever you run the `docker` command, add your username to the __docker__ group:

```
$ sudo usermod -aG docker ${USER}
```

To apply the new group membership, log out of the server and back in, or type the following:

```
$ su - ${USER}
```

You will be prompted to enter your user's password to continue.

Confirm that your user is now added to the __docker__ group by typing:

```
$ id -nG
```

```
sammy sudo docker
```

If you need to add a user to the __docker__ group that you're not logged in as, declare that username explicitly using:

```
$ sudo usermod -aG docker username
```

## Commands

Using `docker` consists of passing it a chain of options and commands followed by arguments. The syntax takes this form:

```
$ docker [option] [command] [arguments]
```

To view all available subcommands, type:

```
$ docker
```

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

Solving error: `bind: address already in use`

Check the process using the address or `PORT` with the command:

```
$ sudo netstat -pna | grep <PORT>
```

If you think is save to stop or kill the process running on the same port, you can use the following command:

```
$ sudo kill `sudo lsof -t -i:<PORT>`
# or
$ sudo kill $(sudo lsof -t -i:<PORT>)
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
