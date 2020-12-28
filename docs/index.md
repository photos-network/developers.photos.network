---
hide:
- navigation
- toc
---
# Developer documentation

This documentation is targeting developers for [Photos.network](https://photos.network) an open source project for self hosted photo management.

!!! hint "Not a developer?"
    If you are interested in hosting your own photos.network at home, visit [our main website](https://photos.network)


### Code of conduct

!!! quote "Why do I need a code of conduct?"
    A code of conduct is a document that establishes expectations for behavior for your project’s participants.

To keep a positive social atmosphere in this project, some decicions and requirements have to be applied:

- [x] write beginner friendly code[^1]
- [x] avoid full-stack frameworks[^2]
- [x] use [PEP 484: Type Hints](https://www.python.org/dev/peps/pep-0484/) in the code syntax.
- [x] follow the [PEP 8: Style Guide](https://www.python.org/dev/peps/pep-0008/) coding conventions.

[^1]: Write clean and maintable code so beginner level programmers can understand it. This can increase the willingness of new contributors.
separate code in packages and classes, write tests
[^2]: full-stack frameworks are great for prototyping and fast development. But often they are coupling many parts.
