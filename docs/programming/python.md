# Python

## Python debugger
* Anywhere that you want to debug, just add this line of code
	
	```
	import ipdb;ipdb.set_trace()
	```
	
* Load in the python file like normal

	```
	python <nameofpythonfile.py>
	```
	
* Run these:

	```
	l (displays +-5 lines around the debug line)
	vars() (displays all loaded vars in memory until this point)
	type(var) (display the type of variable)
	from IPython import embed
	embed() (Drop into iPython shell within ipdb)
	Ctrl+d to drop back into ipdb
	```