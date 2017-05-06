-----------------------------------------------
Development Buildout for Spacedate web application
-----------------------------------------------

Environment
===========

An Ubuntu development environment is assumed.

We use the system Python and Postgresql packages.

These Ubuntu packages should be installed if they aren't already on your
machine::

    - build-essential
    - libffi-dev
    - libmagickwand-dev
    - libpq-dev
    - libxml2-dev
    - libxslt-dev
    - postgresql
    - python2.7
    - python2.7-dev
    - virtualenv

Quick Start
===========

Run buildout in a virtual environment::

    $ virtualenv -p python2.7 .
    $ bin/pip install zc.buildout
    $ bin/buildout

Make sure you have a postgresql superuser with the same name as your unix
user::
    
    $ sudo -u postgres createuser -s <username>

Create a database::

    $ createuser -P spacedev
    (Password: spacedev)
    $ createdb -O spacedev spacedb

Initialize or upgrade tables::

    $ bin/alembic -c etc/space.ini upgrade head

//TODO Initially, the database will be empty. Test data can be added by running::

//TODO     $ bin/sample_data etc/space.ini

Run the application::

    $ bin/pserve etc/carts.ini

Visit: http://localhost:6543/

