Claremont Humans versus Zombies Site
====================================

This is the website for the Claremont College's biannual HvZ game.

Dev machine setup
-----------------

Developing for the site will require [Django] [4], [VirtualEnv] [3],
and [Compass] [5]. If you are familiar with and have (or know how to
get) all of these, feel free to skip this section.

First off, install [pip] [1] using your favorite package manager. If
you're developing on a Mac, I recommend installing/using [homebrew]
[2] as your package manager of choice. Then `brew install python` will
install pip.

Using pip, you should have an easy time installing virtualenv:

    pip install virtualenv

Building the site
-----------------

Now create a root directory for your site. Mine is
`~/programming/claremonthvz.org`.

Note that I'm going to refer to `~/programming` everywhere. If your
root directory is in a different place, use your imagination and
substitute accordingly.

Now build a virtualenv in the root directory, which for me was

    virtualenv ~/programming/claremonthvz.org

Virtualenv provides a wrapper between your machine and the site. As
long as the site only interacts with packages inside this wrapper, we
know that we can port the site over to other machines without
accidentally relying on some random laptop's quirks.

To actually *use* the virtualenv, you'll need to activate it:

    source ~/programming/claremonthvz.org/bin/activate

This command only affects your current terminal, so you'll need to
rerun it every time you want to work on the site. I highly recommend
you add an alias to your .bashrc along the lines of

    alias hvz="cd ~/programming/claremonthvz.org && source bin/activate && cd claremontHvZ/HVZ"

Clone your forked GitHub repo (you don't have to use the command line
for this):

    git clone git@github.com:MYUSERNAME/claremontHvZ.git

Now complete the build with

    python ~/programming/claremonthvz.org/HVZ/HVZ/scripts/setup.py

If all went well, that should be it!

### Running a development version of the server

To run a development version of the server:

    python manage.py runserver

You can then access the site by directing your browser to `localhost:8000`.

### Running unit tests

To run our unit tests:

    python manage.py test HVZ

These tests will check registration, feeding, and permission scenarios.


[1]: http://www.pip-installer.org/ "PyPI Package Manager"
[2]: http://mxcl.github.io/homebrew/ "Homebrew"
[3]: https://pypi.python.org/pypi/virtualenv/ "VirtualEnv"
[4]: https://www.djangoproject.com/ "Django"
[5]: https://rubygems.org/gems/compass "Compass"
