.. _getting_started:

========================================================================
Getting started
========================================================================

.. _installing-docdir:

Installing your doc directory
------------------------------------------------------------------------

You may already have sphinx `sphinx <http://sphinx.pocoo.org/>`_
installed -- you can check by doing::

  python -c 'import sphinx'

If that fails grab the latest version of and install it with::

  > easy_install -U Sphinx

Now you are ready to build a template for your docs, using
sphinx-quickstart::
  
  > mkdir docs
  > cd docs
  docs> sphinx-quickstart

This will walk you through creating the basic configuration; in most cases, you can just accept the defaults.  I choose "website develop" as the name of my project.  When it¡¯s done, you¡¯ll have ``an index.rst``, a ``conf.py`` and some other files. Add these to revision control.


The ``index.rst`` is the master ReST for your project, Include as much detail as you like (refer to the reStructuredText_ syntax or `this template`_ if you need help). edit and add some information ablut your project, Build them to see how they look::

  make html

.. _Write-Your-Docs:

Write Your Docs
------------------------------------------------------------------------

Edit your files and rebuild until you like what you see, Then to modify :file:`index.rst` to include the :file:`getting_started.rst` file (be careful with the indentation, the
"g" in "getting_started" should line up with the ':' in ``:maxdepth``::

  Contents:

  .. toctree::
     :maxdepth: 2

     getting_started.rst

and then rebuild the docs::

  cd docs
  make html

When you reload the page by refreshing your browser pointing to :file:`_build/html/index.html`, you should see a link to the "Getting Started" docs, and in there this page with the screenshot.  `Voila!`

Note we used the image directive to include to the screenshot above with::

  .. image:: _static/basic_screenshot.png

If you now point your browser to :file:`_build/html/index.html`, you should see a basic sphinx site.

.. image:: _static/basic_screenshot.png

The last step commit your changes and push to your public repository. Once you have Sphinx documentation in a public repository, you can start using Read the Docs.


.. _Running-with-RTD:

Running with Read the Docs.
------------------------------------------------------------------------

`Sign up`_ for an account on RTD, then `log in`_. Visit your dashboard_ and click
Import_ to add your project to the site. Fill in the name and description, then
specify where your repository is located. This is normally the URL or path name
you'd use to checkout, clone, or branch your code. Some examples:

* Git: ``http://github.com/ericholscher/django-kong.git``
* Subversion: ``http://varnish-cache.org/svn/trunk``
* Mercurial: ``https://bitbucket.org/ianb/pip``
* Bazaar: ``lp:pasta``

Add an optional homepage URL and some tags, then click "Create".

Within a few minutes your code will automatically be fetched from your public
repository, and the documentation will be built. Check out our :doc:`builds` page to learn more about how we build your docs, and to troubleshoot any issues that arise.

If you want to keep your code updated as you commit, configure your code repository to hit our `Post Commit Hooks`_. This will rebuild your docs every time you push your code.

.. _Sphinx: http://sphinx.pocoo.org/
.. _reStructuredText: http://sphinx.pocoo.org/rest.html
.. _this template: http://docs.writethedocs.org/en/latest/writing/beginners-guide-to-docs/#id1
.. _Sign up: http://readthedocs.org/accounts/register
.. _log in: http://readthedocs.org/accounts/login
.. _dashboard: http://readthedocs.org/dashboard
.. _Import: http://readthedocs.org/dashboard/import
.. _Post Commit Hooks: http://readthedocs.org/docs/read-the-docs/en/latest/webhooks.html 

