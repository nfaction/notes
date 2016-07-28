# Vim Notes

## Formatting

* <http://vim.wikia.com/wiki/Converting_tabs_to_spaces>

## Themes

* <http://www.mkyong.com/linux/how-to-install-a-vim-color-scheme/>
	
	```
	mv ~/Downloads/vim-distinguished-develop/colors/*.vim ~/.vim/colors/
	syntax on
	colorscheme distinguished
	
	OR
	
	:colorscheme smyck
	```

## Tricks

* Multiple windows
	* :Rex (Opens file explorer within current window)
	* :Sex (Opens file explorer in separate split window)
* Block Comment

	```
	Ctrl+v
	Select Text
	Shift+I
	#
	ESC
	```

* Terminal command
	* :! <command>
* Hidden Characters
	* :set list
* Split Panes
	* Horizontal:
		* :sp <filename>
	* Vertical
		* :vsp <filename>
* Delete to space
	* dt <char> or space
* Ctrl+x, Ctrl+e, edit file, then :wq to run command
* :normal <vim commands>
* :reg or :registers
* :set relativenumber
* :r!ls -l (loads output into vim)
* :!<bash command> (run, then go back)
* :Man man (Opens into split window)
	* :source $VIMRUNTIME/ftplugin/man.vim
* vim -p *.js (load into tabs)
	* gt to switch tabs
* Edit path in INSERT MODE, Ctrl+x, Ctrl+f
* Case insensitive search: <http://stackoverflow.com/questions/2287440/how-to-do-case-insensitive-search-in-vim>
  
  ```
  You need to use the \c escape sequence. So:

  /\ccopyright
  ```

