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
	
## JSON

* <http://docs.python-guide.org/en/latest/scenarios/json/>

### Dependencies

```
pip install ipython requests
```


### Code
``` python
import requests
import json

therm="http://192.168.1.XXX/tstat"

t = requests.get(therm)

In  : t.text
Out : u'{"temp":76.50,"tmode":2,"fmode":0,"override":0,"hold":0,"t_cool":76.00,"tstate":0,"fstate":0,"time":{"day":2,"hour":21,"minute":54},"t_type_post":0}'

j = json.loads(t.text)

In  : j
Out :
{u'fmode': 0,
 u'fstate': 0,
 u'hold': 0,
 u'override': 0,
 u't_cool': 76.0,
 u't_type_post': 0,
 u'temp': 76.0,
 u'time': {u'day': 3, u'hour': 22, u'minute': 35},
 u'tmode': 2,
 u'tstate': 0}

In  : j['temp']
Out : 77.0
```