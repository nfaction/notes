# tmux Tips and Tricks
## Helpful Sites

* <https://gist.github.com/MohamedAlaa/2961058>
* <http://www.dayid.org/os/notes/tm.html>
* <https://github.com/tmux-plugins/tmux-resurrect>
* <https://github.com/tmux-plugins/tmux-continuum>
## Detach all other users

```
tmux a -td <session-name>

a=attach
d=detach other clinents (so only you can attach to this session)
t=target
```

<http://stackoverflow.com/questions/22138211/how-do-i-disconnect-all-other-users-in-tmux>


## Tips

* bind fn keys: <http://manoftoday.wikidot.com/tmux>
* status bar: <http://nakkaya.com/2014/01/05/tmux-configuration/>
* reload: <http://zanshin.net/2013/09/05/my-tmux-configuration/>
* <https://gist.github.com/jmatt/5552486>
* Initial attach

	```
	tmux a
	```

* List tmux sessions

	```
	tmux ls
	```
	
* Attach to specific session
	
	```
	tmux a -t session
	```

* Tabs
	* c  new window
	* w  list windows
	* f  find window
	* ,  name window
	* &  kill window
* Panes
	* Broadcast input: Ctrl+B, then ":setw synchronize-panes" (http://blog.sanctum.geek.nz/sync-tmux-panes/)
		* Set on/off: :setw synchronize-panes on/off
			
			```
			c  new window
			w  list windows
			f  find window
			,  name window
			&  kill window
			```
			
* Resize panes

	```
	PREFIX : resize-pane -D (Resizes the current pane down)
	PREFIX : resize-pane -U (Resizes the current pane upward)
	PREFIX : resize-pane -L (Resizes the current pane left)
	PREFIX : resize-pane -R (Resizes the current pane right)
	PREFIX : resize-pane -D 20 (Resizes the current pane down by 20 cells)
	PREFIX : resize-pane -U 20 (Resizes the current pane upward by 20 cells)
	PREFIX : resize-pane -L 20 (Resizes the current pane left by 20 cells)
	PREFIX : resize-pane -R 20 (Resizes the current pane right by 20 cells)
	PREFIX : resize-pane -t 2 20 (Resizes the pane with the id of 2 down by 20 cells)
	PREFIX : resize-pane -t -L 20 (Resizes the pane with the id of 2 left by 20 cells)
	```