=====================
 Installing Trean H5
=====================

:Contact: horde@lists.horde.org

.. contents:: Contents
.. section-numbering::

This document contains instructions for installing the Trean web-based
bookmarks application on your system.

For information on the capabilities and features of Trean, see the
file README_ in the top-level directory of the Trean distribution.


Prerequisites
=============

To function properly, Trean **requires** the following:

1. A working Horde installation.

   Trean runs within the `Horde Application Framework`_, a set of common tools
   for web applications written in PHP.  You must install Horde before
   installing Trean.

   .. Important:: Trean H5 requires version 5.0.2+ of the Horde Framework -
                  earlier versions of Horde will **not** work.

   .. Important:: Be sure to have completed all of the steps in the
                  `horde/doc/INSTALL`_ file for the Horde Framework before
                  installing Trean. Many of Trean's prerequisites are also
                  Horde prerequisites. Additionally, many of Trean's optional
                  features are configured via the Horde install.

   .. _`Horde Application Framework`: http://www.horde.org/apps/horde

The following non-PHP prerequisites are **RECOMMENDED**:

1. ElasticSearch server.

   An ElasticSearch_ server or cluster running on localhost can be used to
   provide indexing of bookmarks data and quick searching of the indexed
   content.

.. _ElasticSearch: http://www.elasticsearch.org/


Installing Trean
================

The **RECOMMENDED** way to install Trean is using the PEAR installer.
Alternatively, if you want to run the latest development code or get the
latest not yet released fixes, you can install Trean from Git.

Installing with PEAR
~~~~~~~~~~~~~~~~~~~~

First follow the instructions in `horde/doc/INSTALL`_ to prepare a PEAR
environment for Horde and install the Horde Framework.

When installing Trean through PEAR now, the installer will automatically
install any dependencies of Trean too. If you want to install Trean with all
optional dependencies, but without the binary PECL packages that need to be
compiled, specify both the ``-a`` and the ``-B`` flag::

   pear install -a -B horde/trean

By default, only the required dependencies will be installed::

   pear install horde/trean

If you want to install Trean even with all binary dependencies, you need to
remove the ``-B`` flag. Please note that this might also try to install PHP
extensions through PECL that might need further configuration or activation in
your PHP configuration::

   pear install -a horde/trean

Installing from Git
~~~~~~~~~~~~~~~~~~~

See http://www.horde.org/source/git.php


Configuring Trean
=================

1. Configuring Trean

   To configure Trean, you must login to Horde as a Horde Administrator.  Use
   the Horde ``Administration`` menu item to get to the administration page,
   and then click on the ``Configuration`` icon to get the configuration page.
   Select ``Bookmarks`` from the selection list of applications, and click on
   the ``Configure`` button.  Fill in or change any configuration values as
   needed.  When done click on ``Generate Bookmarks Configuration`` to
   generate the ``conf.php`` file.  If your web server doesn't have write
   permissions to the Trean configuration directory or file, it will not be
   able to write the file.  In this case, go back to ``Configuration`` and
   choose one of the other methods to create the configuration file
   ``trean/config/conf.php``.

   Documentation on the format and purpose of the other configuration files in
   the ``config/`` directory can be found in each file. You may create
   ``*.local.php`` versions of these files if you wish to customize Trean's
   appearance and behavior. See the header of the configuration files for
   details and examples. The defaults will be correct for most sites.


Obtaining Support
=================

If you encounter problems with Trean, help is available!

The Horde Frequently Asked Questions List (FAQ), available on the Web at

  http://wiki.horde.org/FAQ

The Horde Project runs a number of mailing lists, for individual applications
and for issues relating to the project as a whole.  Information, archives, and
subscription information can be found at

  http://www.horde.org/community/mail

Lastly, Horde developers, contributors and users may also be found on IRC,
on the channel #horde on the Freenode Network (irc.freenode.net).

Please keep in mind that Trean is free software written by volunteers.  For
information on reasonable support expectations, please read

  http://www.horde.org/community/support

Thanks for using Trean!

The Trean team


.. _README: README
.. _`horde/doc/INSTALL`: ../../horde/doc/INSTALL
.. _`horde/doc/TRANSLATIONS`: ../../horde/doc/TRANSLATIONS
