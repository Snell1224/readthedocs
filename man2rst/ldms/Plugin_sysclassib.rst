===
Plugin_sysclassib
===

:Date: 10 Feb 2018

.. contents::
   :depth: 3
..

NAME
====

Plugin_sysclassib - man page for the LDMS sysclassib plugin

SYNOPSIS
========

| Within ldmsd_controller or in a configuration file
| config name=sysclassib [ <attr> = <value> ]

DESCRIPTION
===========

The sysclassib plugin provides IB metric information in raw and rate
(per second) forms.

CONFIGURATION ATTRIBUTE SYNTAX
==============================

The sysclassib plugin uses the sampler_base base class. This man page
covers only the configuration attributes, or those with default values,
specific to the this plugin; see ldms_sampler_base.man for the
attributes of the base class.

**config**\ name=<plugin_name>\ **[schema=<sname>]**\ ports=<ports>\ **[metrics_type=<mtype>]**
   | 
   | configuration line

   name=<plugin_name>
      | 
      | This MUST be sysclassib.

   metrics_type=<metrics_type>
      | 
      | Values are 0 or 1. 0 = counter data only. 1 = include rate data
        (per second) in addition. Default is 0.

   ports=<ports>
      | 
      | CSV list of the form CARD1.PORT1,CARD2.PORT2. Default is all
        discovered values.

BUGS
====

No known bugs.

EXAMPLES
========

Within ldmsd_controller or a configuration file:

::

   load name=sysclassib
   config name=sysclassib component_id=1 producer=vm1_1 instance=vm1_1/sysclassib metric_type=1
   start name=sysclassib interval=1000000 offset=0

SEE ALSO
========

ldms(7), Plugin_procnetdev(7), ldms_sampler_base(7)
