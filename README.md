Flask Empty
===========
Flask-Empty is a simple **flask skeleton** project for fast flask prototyping. Just
clone the project and copy the example you like the most.

Usage
=====
Clone the repository. In **src/** folder, copy somewhere else the flask-version example that you want
to work with. Rename the folder to your project name. Change configurations from _config.py_ to your needs and have fun! = ]

Configuring
===========

First, install the requirement file that you need from the **requirements/** folder. Right now, dev.txt and prod.txt
do the same thing, so you can install either. Change them, and common.txt, to your needs.

```
pip install -r requirements/dev.txt # install dev environment
```

**src/config.py** has some pre-set flask configuration classes for you. They're are all self explanatory.
**Dev** is used by default with the runserver command, while **Testing** is used only when running tests. **Config**
is a more general configuration. You can extend any of these classes to create your production config or some
other special configuration.

Note that the Flask-Script option, -d (disable debug) does not work as expected in Flask-Empty. If you want
to start a non-debug internal server instance, use the **config.Config** configuration or write your own. Example:

```python
# loads config.Config configuration, which has DEBUG=False
# -r is the Flask-Script option for internal server no-reload
python manage.py -r -c Config
```

If environment config named APP_CONFIG is set (as explained here http://flask.pocoo.org/docs/config/#configuring-from-files),
it is used and overwrites any other set configuration.

Templates
=========
There are some error templates bundled with flask-empty by default. All empty right now. Just fill them up for
your project.

Blueprints
==========
Add your blueprints through the src/config.ConfigClass.BLUEPRINTS. A blueprint can be add using the path to the
associated Blueprint instance like **blog.app** where **blog** is a blueprint module and **app** is a
blueprint instance. See **examples/blog_example** for a "full example".

SQLAlchemy
==========
Flask-Empty comes with some Flask-SQLAlchemy configurations ready for you. Just uncomment some lines in your **main.py**
and **database.py** files.

_ps: your models will only be created if they are imported somewhere in your application. By **somewhere**, try the_
_same module where your Blueprint instance is defined._

Examples
========
If my explanation above is as crappy as I think it is, you're gonna want/need to take a look at **examples/**. They
are a very nice starting point to learn how to configure your project. Wort-case-scenario, just copy it, rename it,
configure it and be happy!
