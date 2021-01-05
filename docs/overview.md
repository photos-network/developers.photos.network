---
hide:
- toc
---
# Overview
[Photos.network](https://photos.network) is planned as a modulare system with heavy focus on customization.
It is separated in:

- [Core](/core/) responsible for tasks e.g.: Authentication, Addons, task processing
- [Addons](/addons/) customizational part of the system wich can easily be extended by users
- [Frontend](/frontend/) App-like Web Application for browsing photos and administrate the system
- [Mobile](/mobile/) Native mobile clients for Android and iOS
- [Supervisor](/supervisor/) Container abstraction to keep the core system up-and-running e.g.: Docker

[^1]: The supervisor will keep the core system up-to-date and package the core system into containers e.g. Docker
