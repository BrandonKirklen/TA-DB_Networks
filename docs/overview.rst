Overview
========

About the TA
------------

The DB Networks DBN-6300 uses syslog to provide event reporting to a central Security Information and Event Management (SIEM) system and to report general system health information. Syslog output is encoded in the Common Event Format (CEF), which allows easy integration into a number of common security information and event management (SIEM) andlog-analysis tools. DB Networks can provide sample integration with popular tools. This manual describes the DBN-6300 syslog messages.


**App Author:**
- Brandon Kirklen -- `Email <mailto:brandon.kirklen@dbnetworks.com>`_ - `Splunk Answers <https://answers.splunk.com/users/474440/brandonkirklen.html>`_ - `Github <https://github.com/BrandonKirklen>`_

Splunk/DBN Version Compatibility
--------------------------------

=============== ============= ============
Splunk Version  App Version   DBN Version
Splunk 6.5.2    1.0.0         2.2.14
=============== ============= ============


Install From Github
-------------------

This TA will soon be avalible on SplunkBase, check back for more. Currently you can clone this github repo into your `$SPLUNK_HOME` folder and then restarting Splunk Enterprise.

**Clone:**::

  git clone https://github.com/DBNetworks/TA-DB_Networks.git TA-DB_Networks
