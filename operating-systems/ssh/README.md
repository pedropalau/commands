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

## Generate a new SSH key

```shell
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
```

This creates a new ssh key, using the provided email as a label.

```shell
> Generating public/private rsa key pair.
```

When you're prompted to "Enter a file in which to save the key," press Enter. This accepts the default file location.

```shell
> Enter a file in which to save the key (/home/you/.ssh/id_rsa): [Press enter]
```

At the prompt, type a secure passphrase:

```shell
> Enter passphrase (empty for no passphrase): [Type a passphrase]
> Enter same passphrase again: [Type passphrase again]
```

> If you leave passphrase empty and press Enter, you will create a new SSH key without passphrase.

## Add SSH key to an ssh-agent

Start the ssh-agent in the background.

```shell
$ eval "$(ssh-agent -s)"
> Agent pid 59566
```

Add your SSH private key to the ssh-agent. If you created your key with a different name, or if you are adding an existing key that has a different name, replace id_rsa in the command with the name of your private key file.

```shell
ssh-add ~/.ssh/id_rsa
```

## Work with SSH key passphrases

You can secure your SSH keys and configure an authentication agent so that you won't have to reenter your passphrase every time you use your SSH keys.

### Add or change a passphrase

You can change the passphrase for an existing private key without regenerating the keypair by typing the following command:

```shell
$ ssh-keygen -p
# Start the SSH key creation process
> Enter file in which the key is (/Users/you/.ssh/id_rsa): [Hit enter]
> Key has comment '/Users/you/.ssh/id_rsa'
> Enter new passphrase (empty for no passphrase): [Type new passphrase]
> Enter same passphrase again: [One more time for luck]
> Your identification has been saved with the new passphrase.
```

If your key already has a passphrase, you will be prompted to enter it before you can change to a new passphrase.
