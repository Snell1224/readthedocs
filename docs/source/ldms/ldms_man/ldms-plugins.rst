============
ldms-plugins
============

:Date: 28 Feb 2018

.. contents::
   :depth: 3
..

NAME
=============

ldms-plugins.sh - Display information on installed LDMSD plugins.

SYNOPSIS
=================

ldms-plugins.sh [OPTION] [NAME]

DESCRIPTION
====================

The ldms-plugins.sh command is used to query ldmsd for information on
installed plugins.

OPTIONS
================

If the NAME is specified, only information for that plugin is displayed.
The names all, store, and sampler are interpreted as described in
ldmsd(8).

-b
   | 
   | Produce brief output, omitting usages.

-n
   | 
   | Produce names only.

EXAMPLES
=================

ldms-plugins.sh -b

ldms-plugins.sh vmstat

ldms-plugins.sh -n sampler

ldms-plugins.sh -n store

NOTES
==============

Error messages from attempting to load plugins may appear if
additionally needed libraries cannot be found. This is usually a bug in
the setting of LD_LIBRARY_PATH.

SEE ALSO
=================

ldmsd(8)
