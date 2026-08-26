gentoo warn that pip should not install package at system level.

install pip:
```
emerge --ask dev-python/pip
```

warn:
- dont use sudo or similar when using pip
- virtual venv is recommended (venv)

#### setup python virtual environment (venv)
- create python venv: `python -m venv /path/to/venv`
	- directory can be named anything other than venv
	- this will create `/bin/activate` and other stuff
- enter python venv: `source /path/to/venv/bin/activate`
	- from now on pip is ready to use inside venv
- to quit venv: `deactivate`

make venv pip package available to other software in that environment
```
export PYTHONPATH="${PYTHONPATH}:/path/to/venv/lib/python-<version>/site-packages/"
```

to create virtual environment with access to system package
```
python -m venv --system-site-packages /path/to/venv
```
