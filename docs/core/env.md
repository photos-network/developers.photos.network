---
hide:
- toc
---
# Prepare setup
Prepare an environment by running:
```shell
$ python3 -m venv venv
$ source ./venv/bin/activate
(venv)$ pip3 install -r requirements_test.txt
```

After the environment is build, install the core:
``` shell
(venv)$ python3 setup.py install
```

## Run
The core can be started from the venv:
``` shell
(venv)$ python3 ./venv/bin/core
```
