# Golang programming language

- [Installation](#installation)

## Installation

### Prerequisites

```
$ sudo apt install wget git
```

### Golang installer

```
$ wget -q https://storage.googleapis.com/golang/getgo/installer_linux
$ chmod +x installer_linux 
```

Run the `installer_linux` executable to install Go on the system

```
$ ./installer_linux 
```

Update the current shell session variables to include `GOPATH`:

```
$ source ~/.bash_profile
```

Check the `go` version:

```
$ go version
```