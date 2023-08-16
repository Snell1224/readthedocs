===
man
===

:Date: 10 May 2018

.. contents::
   :depth: 3
..

NAME
====

ldms_auth_munge - LDMS authentication using munge

SYNOPSIS
========

*ldms_app* **-a munge [-A socket=**\ *PATH*\ **]**

DESCRIPTION
===========

**ldms_auth_munge** relies on **munge** service (see **munge**\ (7)) to
authenticate users. Munge daemon (**munged**) must be up and running.
The optional **socket** option can be used to specify the path to munged
unix domain socket in the case that munged wasn't using the default
path.

SEE ALSO
========

**munge**\ (7), **munged**\ (8)
