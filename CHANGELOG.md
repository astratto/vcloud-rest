Changes
==
2013-05-13 (0.2.2)
--

FIXES:

* Fix retrieving of 'ipAddress' attribute of VMs inside VAPP

VARIOUS:

* Add license field to gemspec
* Bump nokogiri dependency to 1.5.9

2012-12-27 (0.2.1)
--

FIXES:

* Fix VM's admin password retrieval

2012-12-21 (0.2.0)
--

FEATURES:

* Allow Task tracking for vApp startup & shutdown
* Improve error message for operations on vApp not running
* Improve error message for access forbidden
* Extend vApp status codes handling
* Add method to show VM's details
* Basic vApp network configuration
* Basic VM network configuration
* Basic Guest Customization configuration

FIXES:

* Show catalog item: fix ID parsing

2012-12-19 (0.1.1)
--

FIXES:

* Fix gemspec URL

2012-12-19 (0.1.0)
--

FEATURES:

* Add support for main operations:
 * login/logout
 * organization _list/show_
 * vdc _show_
 * catalog _show_
 * catalog item _show_
 * vapp _create/delete/startup/shutdown_

2012-12-14 (0.0.1)
--

* Initial release
