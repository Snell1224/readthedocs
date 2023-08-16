===
man
===

:Date: 28 Feb 2018

.. contents::
   :depth: 3
..

NAME
====

ldms_authentication - Authentication in LDMS transports

DESCRIPTION
===========

LDMS applications use authentication plugins in LDMS transports to
authenticate the peers. In other words, not only **ldmsd** authenticates
the client connections, the clients (**ldms_ls**, **ldmsctl**,
**ldmsd_controller**, and other **ldmsd**) authenticate the **ldmsd**
too.

**ldmsd**, **ldms_ls**, **ldmsd_controller**, and **ldmsctl** use the
following options for authentication purpose:

**-a** *AUTH_PLUGIN*
   Specifying the name of the authentication plugin. The default is
   "none" (no authentication).

**-A** *NAME*\ **=**\ *VALUE*
   Specifying options to the authentication plugin. This option can be
   given multiple times.

**auth** configuration object has been introduced in **ldmsd** version
4.3.4. It describes an authentication domain in the configuration file
with **auth_add** command. **listen** and **prdcr_add** config commands
can refer to **auth** object created by **auth_add** command to specify
the authentication domain a listening port or a producer connection
belong to. If no **auth** option is specified, **listen** and
**prdcr_add** commands fall back to use the authentication method
specified by **-a, -A** CLI options (which is default to **none**).

Please consult the manual of the plugin for more details.

LIST OF LDMS_AUTH PLUGINS
=========================

**none**
   Authentication will NOT be used (allow all connections) (see
   **ldms_auth_none**\ (7)).

**ovis**
   The shared secret authentication using ovis_ldms (see
   **ldms_auth_ovis**\ (7)).

**naive**
   The naive authentication for testing. (see **ldms_auth_naive**\ (7)).

**munge**
   User credential authentication using Munge. (see
   **ldms_auth_munge**\ (7)).

SEE ALSO
========

**ldms_auth_none**\ (7), **ldms_auth_ovis**\ (7),
**ldms_auth_naive**\ (7), **ldms_auth_munge**\ (7), **ldmsctl**\ (8),
**ldmsd**\ (8), **ldms_ls**\ (8), **ldmsd_controller**\ (8),
**ldms_quickstart**\ (7), **ldms_build_install**\ (7)
