# Terminal

## Basics

* Keyboard shortcuts
	* Ctrl + - (Undo Command)
	* Ctrl + y (paste yank)
	* Ctrl + k (delete to end)
	* Ctrl + u (delete to beginning)
	* Meta (Using Alt) will do all the above, but by words, not characters
	* Movement
		* d - forward delete
		* f - forward delete
		* b - backwards delete
		* h - back delete
* Search man
	* man -k
* Search files (like spotlight for terminal)
	* `locate`
	* If db out of date, run `updatedb`
* Fixer for all: <https://github.com/nvbn/thefuck>

## Tips/Tricks

```
#protip
Add this to your .bashrc file:
# Ubuntu:
## arrow up
bind '"\eOA": history-search-backward'
## arrow down
bind '"\eOB": history-search-forward'
# Mac OS X:
## arrow up
bind '"\e[A": history-search-backward'
 
## arrow down
bind '"\e[B": history-search-forward'
Type the first character(s) of something you want to find in your history and press the 'up' arrow :arrow_up:
```