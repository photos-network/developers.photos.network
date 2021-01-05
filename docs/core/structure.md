---
hide:
- toc
---
# Structure
Since the core system is responsible for multiple tasks,
it is mandatory to keep the file structure clean and well arranged.

The project itself has a default python application file structure.
```shell
core/
├── core/
├── tests/
├── setup.cfg
└── setup.py
```

inside the core package all necessary files are structured inside subfolders. 
```shell
core/
└── core/
    ├── __main__.py
    ├── addon.py
    ├── addons/
    ├── authentication/
    ├── authorization/
    ├── configs.py
    ├── const.py
    ├── core.py
    ├── loader.py
    ├── persistency/
    ├── utils/
    └── webserver/
```
               
| File | Description |
| ---  | --- |
| \__main__.py | is the entry point and will only read the configuration file and create an application instance. |
| core.py | will monitor the application state and manage all base tasks e.g. setup and load **addons** and starting the **webserver**. |
| addon.py | defines how addons are loaded |
| config.py | abstracts the RuntimeConfiguration and Configuration |
| const.py | contains development constants e.g.: versions |
| core.py | application logic |
| loader.py | helper to load addons |

