.. _running-symfony2-tests:

Running Symfony Tests
=====================

The Symfony project uses a third-party service which automatically runs tests
for any submitted :doc:`patch <patches>`. If the new code breaks any test,
the pull request will show an error message with a link to the full error details.

In any case, it's a good practice to run tests locally before submitting a
:doc:`patch <patches>` for inclusion, to check that you have not broken anything.

.. _phpunit:
.. _dependencies_optional:

Before Running the Tests
------------------------

To run the Symfony test suite, `install PHPUnit`_ 4.2 (or later) first. Then,
install the external dependencies used during the tests, such as Doctrine, Twig
and Monolog. To do so, :doc:`install Composer </cookbook/composer>` and execute
the following:

.. code-block:: bash

    $ composer install

.. _running:

Running the Tests
-----------------

Then, run the test suite from the Symfony root directory with the following
command:

.. code-block:: bash

    $ phpunit

The output should display ``OK``. If not, read the reported errors to figure out
what's going on and if the tests are broken because of the new code.

.. tip::

    The entire Symfony suite can take up to several minutes to complete. If you
    want to test a single component, type its path after the ``phpunit`` command,
    e.g.:

    .. code-block:: bash

        $ phpunit src/Symfony/Component/Finder/

.. _`install PHPUnit`: https://phpunit.de/manual/current/en/installation.html
