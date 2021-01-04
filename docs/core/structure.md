---
hide:
- toc
---
# Structure
```shell
core/
├── core/
│   ├── __main__.py
│   ├── addon.py
│   ├── addons/
│   ├── authentication/
│   ├── authorization/
│   ├── configs.py
│   ├── const.py
│   ├── context.py
│   ├── core.py
│   ├── loader.py
│   ├── persistency/
│   ├── utils/
│   └── webserver/
│
├── tests/
│
├── setup.cfg
└── setup.py
```

Since the core system is responsible for multiple tasks,
it is mandatory to keep the file structure clean and well arranged.

Each main responsibility has its own subfolder e.g.: authentication, authorization

The `__main__.py` is the entry point and will only read the configuration file and create an application instance.

`core.py` will monitor the application state and manage all base tasks e.g. setup and load **addons** or start the **webserver**.

How addons are loaded will be found in `addon.py`

