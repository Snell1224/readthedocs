==============
Plugin_meminfo
==============

:Date: 04 Feb 2018

.. contents::
   :depth: 3
..

NAME
===============

Plugin_meminfo - man page for the LDMS meminfo plugin

SYNOPSIS
===================

| Within ldmsd_controller or a configuration file:
| config name=meminfo [ <attr>=<value> ]

DESCRIPTION
======================

With LDMS (Lightweight Distributed Metric Service), plugins for the
ldmsd (ldms daemon) are configured via ldmsd_controller or a
configuration file. The meminfo plugin provides memory info from
/proc/meminfo.

CONFIGURATION ATTRIBUTE SYNTAX
=========================================

The meminfo plugin uses the sampler_base base class. This man page
covers only the configuration attributes, or those with default values,
specific to the this plugin; see ldms_sampler_base.man for the
attributes of the base class.

**config**
   | name=<plugin_name> [schema=<sname>]
   | configuration line

   name=<plugin_name>
      | 
      | This MUST be meminfo.

   schema=<schema>
      | 
      | Optional schema name. It is intended that the same sampler on
        different nodes with different metrics have a different schema.
        If not specified, will default to \`meminfo\`.

BUGS
===============

No known bugs.

EXAMPLES
===================

Within ldmsd_controller or a configuration file:

::

   load name=meminfo
   config name=meminfo producer=vm1_1 instance=vm1_1/meminfo
   start name=meminfo interval=1000000

SEE ALSO
===================

ldmsd(8), ldms_quickstart(7), ldmsd_controller(8), ldms_sampler_base(7)
