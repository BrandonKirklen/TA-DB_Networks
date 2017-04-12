Getting Started
===============

DBN TA Source Types
----------------------

Splits incoming feed into:

1. ``system_counters``: This source type is used for various system counter information including
	- ``cnt``: An external dump of the internal counter's page, lists stats for incoming feed and engine processing
	- ``sys``: Contains system level information including free memory, cache, and system uptime
	- ``slowsys``: A more complete set of system level information including airflow readings, disk usage, and wear indicators
	- ``dbfwsys``: Information specific to the DBFW process running
2. ``sqli_events``: SQL injection events will be associated with this sourcetype. This includes two subevent types
	- ``distinct_event``: description of the first sql statement which is deemed a potential sql injection attack
	- ``repeat_event``: events which match an injection on a statement already alerted on
3. ``discovery_events``: These alerts are triggered in response to new events within the flows being monitored but without rising to the level of an attack.
	- ``mds_new_user``: A new user is seen for the first time
	- ``mds_new_service``: a new service is seen for the first time
	- ``mds_new_host``: a new host is seen for the first time
	- ``mds_new_listener``: a new listener is seen for the first time
	- ``tally_new_ipseity``: a new context is seen linking client and servicer in dimensions (tally board, user, service, client, server)
4. ``health_events``: contains events mainly involving engineering metrics
	- ``heart_beat``: used to monitor system up status on a more frequent basis than ``dbfwsys``
	- ``engine_start``: used to monitor for engine restarts
	- ``archive``: Indicates status of overnight system archive tool
	- ``dbfw_gc``: Indicates a system restart due to overload of data
	- ``dbdu``: postgres database disk usage
5. ``insider_threat_events``: events related to table level analysis preformed with the insider threat module
6. ``audit``: events exported by native device auditing
7. ``upgrade``: raw dump of upgrade messages for external viewing
8. ``internal``: catch for bad output of internal messages, trashed


DBN 6300 Message Overview
-------------------------

Syslog messages forwarded from the DBN-6300 are formatted to meet the CEF specification.

Syslog Message Format:

+------------------+--------------------------------------+
| CEF Header Field | DBN-6300 Data                        |
+==================+======================================+
| Version          | 0                                    |
+------------------+--------------------------------------+
| Device Vendor    | DB Networks                          |
+------------------+--------------------------------------+
| Device Product   | ADF                                  |
+------------------+--------------------------------------+
| Device Version   | Current system version               |
+------------------+--------------------------------------+
| Signature ID     | Numeric ID                           |
+------------------+--------------------------------------+
| Name             | String name associated with ID       |
+------------------+--------------------------------------+
| Severity         | Value from 0-10, system specified    |
+------------------+--------------------------------------+
| cs1Label         | system identifier                    |
+------------------+--------------------------------------+
| cs1              | System serial number                 |
+------------------+--------------------------------------+
| Message          | Varies by event                      |
+------------------+--------------------------------------+

Signature ID and Name Values
----------------------------

+--------------+-----------------------------+----------------------------------------------+
| Signature ID | Name                        | Description                                  |
+==============+=============================+==============================================+
| 0            | distinct_event              | New system events                            |
+--------------+-----------------------------+----------------------------------------------+
| 1            | repeat_event                | A count of repeaded events                   |
+--------------+-----------------------------+----------------------------------------------+
| 2            | heart_beat                  | Used in 1.0-1.3 to report system health      |
+--------------+-----------------------------+----------------------------------------------+
| 3            | engine_start                | A system has powered up or restarted         |
+--------------+-----------------------------+----------------------------------------------+
| 4            | archive                     | Indicates status of overnight system archive tool |
+--------------+-----------------------------+----------------------------------------------+
| 5            | dbfw_gc                     | Indicates a system restart due to overload of data  |
+--------------+-----------------------------+----------------------------------------------+
| 6            | mds_new_user                | A new user identified                        |
+--------------+-----------------------------+----------------------------------------------+
| 7            | mds_new_service             | A new service identified                     |
+--------------+-----------------------------+----------------------------------------------+
| 8            | mds_new_host                | A new host identified                        |
+--------------+-----------------------------+----------------------------------------------+
| 9            | mds_new_listener            | A new listener identified                    |
+--------------+-----------------------------+----------------------------------------------+
| 10           | tally_new_ipseity           | Detailed info on new connections             |
+--------------+-----------------------------+----------------------------------------------+
| 11           | cnt                         | System health counters                       |
+--------------+-----------------------------+----------------------------------------------+
| 12           | sys                         | System health counters                       |
+--------------+-----------------------------+----------------------------------------------+
| 13           | slowsys                     | System health counters                       |
+--------------+-----------------------------+----------------------------------------------+
| 14           | dbfwsys                     | System health counters                       |
+--------------+-----------------------------+----------------------------------------------+
| 15           | internal                    | Trashed messages from debug                  |
+--------------+-----------------------------+----------------------------------------------+
| 16           | cnta                        | Full counter dump                            |
+--------------+-----------------------------+----------------------------------------------+
| 17           | dbhealth                    | Database health status in csv                |
+--------------+-----------------------------+----------------------------------------------+
| 18           | it_threat_event             | Events related to IT Module                  |
+--------------+-----------------------------+----------------------------------------------+
| 19           | upgrade                     | System upgrade messages                      |
+--------------+-----------------------------+----------------------------------------------+
| 20           | audit                       | System audit messages                        |
+--------------+-----------------------------+----------------------------------------------+
| 21           | dbdu                        | Postgres table disk usage                    |
+--------------+-----------------------------+----------------------------------------------+

.. note:: The default size of the rsyslog is 8K.
   Logs that exceed this size are truncated automaticaly.
   If you expect syslog messages greater than 8K,
   increase the default message size to avoid truncation.

DBN-6300 Syslog Message Detail
------------------------------

Engine Restart Message
**********************

The restart message the startup of the DBN-6300. This message indicates that the
DBN-6300 has completed its power up sequence after an initial power-up, restart/reset,
orfatal error. If this message isdetected and no intentional restart was initiated,
contact customer service to investigate the cause.

A typical message resembles the following::

  2017-03-14T18:57:33.449245-05:00 dbfw adf: CEF:0|DB Networks|ADF|2.2.13|3|engine_start|
  5|cs1Label=system identifier cs1=00:00:00:00:00:00

The message is identified by Signature ID=``3`` and name=``engine_start``.

Event Report Messages
*********************

Event report messages are generated as soon as an event is detected. There are two
types of event report messages:

- ``distinct_event`` messages pertain to new unique SQL statements that are detected
  as possible threates. Distinct events have a Signature ID=``0`` and name=``distinct_event``
- ``repeat_event`` messages represent repeated executions of previously detected SQL statements.
  Repeat events have a Signature ID=``1`` and name=``repeat_event``

Both messages contain the same information, but are distinguished by the labels above appearing in the name field of the CEF prefix.

A typical ``distinct_event`` resembles the following. A ``repeat_event`` has the same structure, but the ``cnt`` field is greater than 1.

::

  2017-03-14T19:27:32.883848-05:00 dbfw adf: CEF:0|DB Networks|ADF|2.2.13|0|distinct_event|
  5|cs1Label=system identifier cs1=00:00:00:00:00:00 externalId=2737 cnt=1 rt=1489537652883
  start=1336602182934 destinationServiceName=master cn1Label=statement identifier cn1=2736
  cat=structural dst=10.10.10.77 dpt=1305 src=10.10.10.186 spt=3585 cs2Label=score cs2=0.500
  cs3Label=confidence cs3=likely act=exec_dispatch target_sql_id=1099

The first part of the message contains the elements of the standard CEF format. The table below descrives the event-specific fields.
