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