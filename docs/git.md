# Git

## Helpful Sites
* <http://git-scm.com/docs/git-stash>
* <http://git-merge.com/>
* <https://githowto.com/getting_old_versions>

## User Management
### Global User

* Changing username on remote box:
	* <https://help.github.com/articles/setting-your-email-in-git/>

	```
	git config --global user.email "your_email@example.com"
	git config --global user.name "Billy Everyteen"
	 
	git config --global user.email "nfaction@gmail.com"
	git config --global user.name "Matt DePorter"
	```

### Changing GitHub Username
<https://help.github.com/articles/what-happens-when-i-change-my-username/>

## Managing branches, remotes and PR

```
git fetch origin dev
 
git remote -v
 
git remote add jetstream https://github.com/jetstream-cloud/atmosphere-ansible.git
 
git fetch jetstream user-accounts
 
git checkout dev
 
git checkout -b user-accounts-feature
 
git cherry-pick -x 298e637418d5ba96e1db5b86cd12f542e2921c56
 
git log
 
git push lenards user-accounts-feature
 
GitHub
 
jetstream-cloud/atmosphere-ansible
 
atmosphere-ansible - Ansible deployment code for Atmosphere
 
[
10:29
]
https://github.com/iPlantCollaborativeOpenSource/atmosphere-ansible/pull/15
 
 
GitHub
 
Switch to AllowGroups instead of AllowUsers by lenards · Pull Request #15 · iPlantCollaborativeOpenSource/atmosphere-ansible · GitHub
 
Added better matching for grep on /etc/groups. Use sshd_config directive for AllowGroups so that adding a user account only consists of a useradd, adding that user to the users group and setting t...
```