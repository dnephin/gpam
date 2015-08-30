
General Purpose Application Manager
===================================

An OS-independent application manager.

What problem does gpam solve?
-----------------------------

You have an application that you'd like to distribute. Using traditional methods
you could provide an operating system specific package (yum, apt, portage,
pacman, homebrew, windows installer, etc) for each operation system you want to
target. Providing a package for every target is a considerable effort.  You
could provide a source distribution, but that leaves a pretty heavy burden
on the users to build from source.

``gpam`` is a system for distributing and managing applications for any
platform that supports docker.


``gpam`` primary targets application, not services, the distinction being
integration with an init system. An application is generally invoked by a user
not by an init system.


Does it replace package managers ?
----------------------------------

No. Package managers are essential for integration with the operating systems
init system. Package managers are likely to be used to build the docker
image that provides the application.


How it works ?
--------------

``gpam`` works with docker images that are published to the docker hub or a
docker registry. It uses a convention


Features
--------

* install applications by pulling images from a docker registry or docker hub
* prompt users during installation for configuration settings
* list installed applications
* uninstall applications


Documentation
-------------

``gpam`` supports the following commands

``gpam install <image tag>``

``gpam upgrade <package name>``

``gpam remove <package name | image tag>``

``gpam list``


Packages
~~~~~~~~



How it works
~~~~~~~~~~~~

``install``

* ``docker pull`` the image
* look for a ``/gpam/manifest``
* if one exists, prompt the user for configuration 
* copy ``gpam`` to a new file in $PATH with the application name
* 



