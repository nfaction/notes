# SSH

## Keys
* Copy SSH key
	
	```
	cat ~/.ssh/id_rsa.pub | ssh $host -p $ssh_port "sd='~/.ssh;mkdir -p $sd;chmod 700 $sd;ccat >> ~/.ssh/authorized_keys;chmod 600 ${sd}/authorized_keys"
	```
* Unlock keychain
	
	```
	security unlock-keychain
	eval `ssh-agent -s`
	```

* Lock keychain
	
	```
	eval `ssh-agent -k`
	security lock-keychain
	```
	
<http://superuser.com/questions/88470/how-to-use-mac-os-x-keychain-with-ssh-keys>

## SSH Config

<http://serverfault.com/questions/139870/stop-ssh-client-from-offering-all-the-public-keys-it-can-find>

Basically, specifying IdentityFiles just adds keys to a current list the SSH agent already presented to the client.

Try overriding this behaviour with this at the bottom of your .ssh/config file:

```
Host *
  IdentitiesOnly yes
```

You can also override this setting on the host level, e.g.:

```
Host foo
  User bar
  IdentityFile /path/to/key
  IdentitiesOnly yes
```