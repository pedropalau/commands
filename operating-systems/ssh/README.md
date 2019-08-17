# SSH

Using the [SSH protocol](https://es.wikipedia.org/wiki/Secure_Shell), you can connect and authenticate to remote servers and services.

## Check for existing SSH keys

```shell
$ ls -al ~/.ssh
# Lists the files in your .ssh directory, if they exist
```

By default, the filenames of the public keys are one of the following:

* id_dsa.pub
* id_ecdsa.pub
* id_ed25519.pub
* id_rsa.pub
