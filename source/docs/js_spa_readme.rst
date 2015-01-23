==============
Javascript SPA
==============

Prerequisites
-------------

Node.js
~~~~~~~

You need to have `Node.js <http://nodejs.org/>`__ and
`npm <https://npmjs.org/>`__ installed on your system.

On Ubuntu, both Node and npm can be installed from apt-get

.. code:: bash

    # Ubuntu
    sudo apt-get install nodejs

On CentOS, you have to install them separately

.. code:: bash

    sudo yum install nodejs npm

Directory
~~~~~~~~~

You must be in the same directory as this ``README.md`` file. From the
project root, run the following:

.. code:: bash

    cd stackdio/server/core/static/stackdio/

Installing stackd.io dependencies
---------------------------------

In your CLI, run the following setup command.

.. code:: bash

    npm run-script setup

Low memory process
------------------

If you are running on a low memory machine, or most of the memory is
already being used while you're trying to install, you may receive the
following message while installing.

.. code:: bash

    Error: spawn ENOMEM

This is caused because ``npm`` and ``bower`` both spawn new processes to
run the install scripts, so if you are geting the error, you can try to
manually run the steps that the setup script runs to conserve memory.

Installing stackd.io npm modules
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

In your CLI, get to the ``core/static/stackdio`` directory and install
all npm modules.

.. code:: bash

    npm install

Installing all Bower components
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Next, you can run a Grunt task, from the same directory, to get all the
Bower components installed.

.. code:: bash

    npm run grunt

Configure Knockout and Q
~~~~~~~~~~~~~~~~~~~~~~~~

All other Bower modules include a minified version out of the box, so we
need to minify Knockout and Q by first going to each module and
installing all the Node modules required.

First we run the build for Knockout which will produce the minified
version.

.. code:: bash

    cd components/knockout
    npm install

Change to the Q directory and run the build command which will create
the minified version.

.. code:: bash

    cd ../q
    npm install
