.. _auditCodes:

Audit Codes
==============================

3.0.0
------

``secOps`` (1000-1999)
*****************

Security Operations (``secOps``):

====== ============================================================ ================
 Code                            Message                                 Target
====== ============================================================ ================
 1000   Create user                                                  User
 1001   Update user                                                  User
 1002   Delete user                                                  User
 1003   Update user's password                                       User
 1004   Lock user                                                    User
 1005   Unlock user                                                  User
 1006   Clear user's failed login attempts                           User
 1007   Clear user's old passwords                                   User
 1008   Logout all users                                             User
 1009   User login succeeded                                         User
 1010   User login failed                                            User
 1011   Logout user                                                  User
 1012   Not authorized                                               User
 1013   Not permitted                                                User
 1014   Create role                                                  Role
 1015   Update role                                                  Role
 1016   Delete role                                                  Role
 1017   Update authentication configuration                          Authentication
 1018   Update tunnel configuration                                  Tunnel
 1019   Update SSL configuration                                     SSL
 1020   Update redaction configuration                               Redaction
 1021   Clear audit log                                              AuditLog
 1022   Update audit configuration                                   AuditLog
 1023   Audit Error                                                  N/A
 1024   Create session                                               Session
 1025   Delete session                                               Session
 1026   Enable SSH remote access                                     SSH
 1027   Disable SSH remote access                                    SSH
 1028   Create API key                                               APIKey
 1029   Update API key                                               APIKey
 1030   Delete API key                                               APIKey
 1031   Lock API key                                                 APIKey
 1032   Unlock API key                                               APIKey
 1033   Update Strict-Transport-Security HTTP header configuration   HSTS
 1034   Update user interface port configuration                     UIPorts
 1035   Update global redaction settings                             GlobalRedation
 1036   Update shell password                                        ShellPassword
 1037   Deleted shell password                                       ShellPassword
====== ============================================================ ================


``sysOps`` (2000-2999)
*****************

System Operations (``sysOps``):

====== ========================================== ===================
 Code                   Message                         Target
====== ========================================== ===================
 2000   Update network configuration               Network
 2001   Update capture filter                      CaptureFilter
 2002   Update capture filter mode                 CaptureFilter
 2003   Create capture VLAN                        CaptureVLAN
 2004   Update capture VLAN                        CaptureVLAN
 2005   Delete capture VLAN                        CaptureVLAN
 2006   Update capture source                      CaptureSource
 2007   Enable capture source identify             CaptureSource
 2008   Disable all capture source identifiers     CaptureSource
 2009   Update NTP configuration                   Time
 2010   Update server time                         Time
 2011   Update server timezone                     Time
 2012   Update syslog configuration                Syslog
 2013   Restart system                             System
 2014   Power system down                          System
 2015   Restart UI server                          System
 2016   Reset to factory configuration             System
 2017   Create system state report                 SystemStateReport
 2018   Delete system state report                 SystemStateReport
 2019   Initialize system for file management      FileManagement
 2020   Upload backup                              Backup
 2021   Delete backup                              Backup
 2022   Download backup                            Backup
 2023   Set password for backup                    Backup
 2024   Unlock backup                              Backup
 2025   Initialize system for restoring a backup   N/A
 2026   Restore backup                             Backup
 2027   Create backup                              Backup
 2028   Upload update                              N/A
 2029   Delete update                              Update
 2030   Apply update                               Update
 2031   Kill watchdog                              Watchdog
 2032   Enable watchdog                            Watchdog
 2033   Disable watchdog                           Watchdog
 2034   Update registry                            Registry
 2035   Update CMS configuration                   CMS
 2036   Create a unit within CMS                   N/A
 2037   Update a unit within CMS                   Unit
 2038   Delete a unit within CMS                   N/A
 2039   User accepted the EULA                     EULA
 2040   EULA covered under seperate agreement      EULA
 2041   Clear user data                            System
 2042   System resource lock debug                 [lockName]
 2043   Delete job                                 Job
 2044   CMDB data was downloaded                   CMDB
 2045   CMDB data was merged into the system       CMDB
 2046   CMDB configuration data was downloaded     CMDB
 2047   CMDB configuration data was loaded         CMDB
 2048   User did not accept the EULA               EULA
====== ========================================== ===================


``appOps`` (3000-3999)
*****************

Application Operations (``appOps``):

======== =========================================== ===================
 Code                      Message                         Target
======== =========================================== ===================
 3000     Map a service to a database                 Mapping
 3001     Unmap a service from a database             Mapping
 3002     Unmanage a service                          Mapping
 3003     Update time period                          TimeLearning
 3004     Commit time learning                        TimeLearning
 3005     Learn statement                             StatementLearning
 3006     Blacklist statement                         StatementLearning
 3007     Update database configuration               Database
 3008     Terminal session started                    Terminal
 3009     Terminal session ended                      Terminal
 3010     Terminal session not authorized             Terminal
 3011     Terminal session not authorized for tail    Terminal
======== =========================================== ===================

``uiCalls`` (4000-4999)
******************

UI Route Details (``uiCalls``):

====== ================
 Code      Message
====== ================
 4000   UI route logs
====== ================


``cliCommands`` (5000-5999)
**********************

Command Line Interface Command Details (``cliCommands``):

====== =====================
 Code         Message
====== =====================
 5000   CLI command run
 5001   CLI command failed
====== =====================


``ldapAuth`` (6000-6999)
********************

LDAP Authentication (``ldapAuth``):

====== ===========================
 Code            Message
====== ===========================
 6000   Ldap authentication logs
====== ===========================


``aclOps`` (7000-7999)
*****************

Access Control List Operations (``aclOps``):

====== ============================
 Code            Message
====== ============================
 7000   Access control list
 7001   Access control list debug
====== ============================


``certOps`` (8000-8999)
******************

Certificate Operations (``certOps``):

====== ===============================
 Code              Message
====== ===============================
 8000   Certificate debug
 8001   Certificate being used
 8002   Certificate has been verified
====== ===============================



2.2.14
------

``secOps`` (1000-1999)
*****************

Security Operations (``secOps``):

+-------+------------------------------------------------------------+----------------+
| Code  | Message                                                    | Target         |
+=======+============================================================+================+
| 1000  | Create user                                                | User           |
+-------+------------------------------------------------------------+----------------+
| 1001  | Update user                                                | User           |
+-------+------------------------------------------------------------+----------------+
| 1002  | Delete user                                                | User           |
+-------+------------------------------------------------------------+----------------+
| 1003  | Update user's password                                     | User           |
+-------+------------------------------------------------------------+----------------+
| 1004  | Lock user                                                  | User           |
+-------+------------------------------------------------------------+----------------+
| 1005  | Unlock user                                                | User           |
+-------+------------------------------------------------------------+----------------+
| 1006  | Clear user's failed login attempts                         | User           |
+-------+------------------------------------------------------------+----------------+
| 1007  | Clear user's old passwords                                 | User           |
+-------+------------------------------------------------------------+----------------+
| 1008  | Logout all users                                           | User           |
+-------+------------------------------------------------------------+----------------+
| 1009  | User login succeeded                                       | User           |
+-------+------------------------------------------------------------+----------------+
| 1010  | User login failed                                          | User           |
+-------+------------------------------------------------------------+----------------+
| 1011  | Logout user                                                | User           |
+-------+------------------------------------------------------------+----------------+
| 1012  | Not authorized                                             | User           |
+-------+------------------------------------------------------------+----------------+
| 1013  | Not permitted                                              | User           |
+-------+------------------------------------------------------------+----------------+
| 1014  | Create role                                                | Role           |
+-------+------------------------------------------------------------+----------------+
| 1015  | Update role                                                | Role           |
+-------+------------------------------------------------------------+----------------+
| 1016  | Delete role                                                | Role           |
+-------+------------------------------------------------------------+----------------+
| 1017  | Update authentication configuration                        | Authentication |
+-------+------------------------------------------------------------+----------------+
| 1018  | Update tunnel configuration                                | Tunnel         |
+-------+------------------------------------------------------------+----------------+
| 1019  | Update SSL configuration                                   | SSL            |
+-------+------------------------------------------------------------+----------------+
| 1020  | Update redaction configuration                             | Redaction      |
+-------+------------------------------------------------------------+----------------+
| 1021  | Clear audit log                                            | AuditLog       |
+-------+------------------------------------------------------------+----------------+
| 1022  | Update audit configuration                                 | AuditLog       |
+-------+------------------------------------------------------------+----------------+
| 1023  | Audit Error                                                | AuditError     |
+-------+------------------------------------------------------------+----------------+
| 1024  | Create session                                             | Session        |
+-------+------------------------------------------------------------+----------------+
| 1025  | Delete session                                             | Session        |
+-------+------------------------------------------------------------+----------------+
| 1026  | Enable SSH remote access                                   | SSH            |
+-------+------------------------------------------------------------+----------------+
| 1027  | Disable SSH remote access                                  | SSH            |
+-------+------------------------------------------------------------+----------------+
| 1028  | Create API key                                             | APIKey         |
+-------+------------------------------------------------------------+----------------+
| 1029  | Update API key                                             | APIKey         |
+-------+------------------------------------------------------------+----------------+
| 1030  | Delete API key                                             | APIKey         |
+-------+------------------------------------------------------------+----------------+
| 1031  | Lock API key                                               | APIKey         |
+-------+------------------------------------------------------------+----------------+
| 1032  | Unlock API key                                             | APIKey         |
+-------+------------------------------------------------------------+----------------+
| 1033  | Update Strict-Transport-Security HTTP header configuration | HSTS           |
+-------+------------------------------------------------------------+----------------+
| 1034  | Update user interface port configuration                   | UIPorts        |
+-------+------------------------------------------------------------+----------------+

``sysOps`` (2000-2999)
*****************

System Operations (``sysOps``):

+------+------------------------------------------+-------------------+
| Code | Message                                  | Target            |
+======+==========================================+===================+
| 2000 | Update network configuration             | Network           |
+------+------------------------------------------+-------------------+
| 2001 | Update capture filter                    | CaptureFilter     |
+------+------------------------------------------+-------------------+
| 2002 | Update capture filter mode               | CaptureFilter     |
+------+------------------------------------------+-------------------+
| 2003 | Create capture VLAN                      | CaptureVLAN       |
+------+------------------------------------------+-------------------+
| 2004 | Update capture VLAN                      | CaptureVLAN       |
+------+------------------------------------------+-------------------+
| 2005 | Delete capture VLAN                      | CaptureVLAN       |
+------+------------------------------------------+-------------------+
| 2006 | Update capture source                    | CaptureSource     |
+------+------------------------------------------+-------------------+
| 2007 | Enable capture source identify           | CaptureSource     |
+------+------------------------------------------+-------------------+
| 2008 | Disable all capture source identifiers   | CaptureSource     |
+------+------------------------------------------+-------------------+
| 2009 | Update NTP configuration                 | Time              |
+------+------------------------------------------+-------------------+
| 2010 | Update server time                       | Time              |
+------+------------------------------------------+-------------------+
| 2011 | Update server timezone                   | Time              |
+------+------------------------------------------+-------------------+
| 2012 | Update syslog configuration              | Syslog            |
+------+------------------------------------------+-------------------+
| 2013 | Restart system                           | System            |
+------+------------------------------------------+-------------------+
| 2014 | Power system down                        | System            |
+------+------------------------------------------+-------------------+
| 2015 | Restart UI server                        | System            |
+------+------------------------------------------+-------------------+
| 2016 | Reset to factory configuration           | System            |
+------+------------------------------------------+-------------------+
| 2017 | Create system state report               | SystemStateReport |
+------+------------------------------------------+-------------------+
| 2018 | Delete system state report               | SystemStateReport |
+------+------------------------------------------+-------------------+
| 2019 | Initialize system for file management    | FileManagement    |
+------+------------------------------------------+-------------------+
| 2020 | Upload backup                            | Backup            |
+------+------------------------------------------+-------------------+
| 2021 | Delete backup                            | Backup            |
+------+------------------------------------------+-------------------+
| 2022 | Download backup                          | Backup            |
+------+------------------------------------------+-------------------+
| 2023 | Set password for backup                  | Backup            |
+------+------------------------------------------+-------------------+
| 2024 | Unlock backup                            | Backup            |
+------+------------------------------------------+-------------------+
| 2025 | Initialize system for restoring a backup | Backup            |
+------+------------------------------------------+-------------------+
| 2026 | Restore backup                           | Backup            |
+------+------------------------------------------+-------------------+
| 2027 | Create backup                            | Backup            |
+------+------------------------------------------+-------------------+
| 2028 | Upload update                            | Update            |
+------+------------------------------------------+-------------------+
| 2029 | Delete update                            | Update            |
+------+------------------------------------------+-------------------+
| 2030 | Apply update                             | Update            |
+------+------------------------------------------+-------------------+
| 2031 | Kill watchdog                            | Watchdog          |
+------+------------------------------------------+-------------------+
| 2032 | Enable watchdog                          | Watchdog          |
+------+------------------------------------------+-------------------+
| 2033 | Disable watchdog                         | Watchdog          |
+------+------------------------------------------+-------------------+
| 2034 | Update registry                          | Registry          |
+------+------------------------------------------+-------------------+

``appOps`` (3000-3999)
*****************

Application Operations (``appOps``):

+------+------------------------------------------+-------------------+
| 3000 | Map a service to a database              | Mapping           |
+======+==========================================+===================+
| 3001 | Unmap a service from a database          | Mapping           |
+------+------------------------------------------+-------------------+
| 3002 | Unmanage a service                       | Mapping           |
+------+------------------------------------------+-------------------+
| 3003 | Update time period                       | TimeLearning      |
+------+------------------------------------------+-------------------+
| 3004 | Commit time learning                     | TimeLearning      |
+------+------------------------------------------+-------------------+
| 3005 | Learn statement                          | StatementLearning |
+------+------------------------------------------+-------------------+
| 3006 | Blacklist statement                      | StatementLearning |
+------+------------------------------------------+-------------------+
| 3007 | Update database configuration            | Database          |
+------+------------------------------------------+-------------------+
| 3008 | Terminal session started                 | Terminal          |
+------+------------------------------------------+-------------------+
| 3009 | Terminal session ended                   | Terminal          |
+------+------------------------------------------+-------------------+
| 3010 | Terminal session not authorized          | Terminal          |
+------+------------------------------------------+-------------------+
| 3011 | Terminal session not authorized for tail | Terminal          |
+------+------------------------------------------+-------------------+

``uiCalls`` (4000-4999)
******************

UI Route Details (``uiCalls``):

+------+---------------+
| Code | Message       |
+======+===============+
| 4000 | UI route logs |
+------+---------------+

``cliCommands`` (5000-5999)
**********************

Command Line Interface Command Details (``cliCommands``):

+------+--------------------+
| Code | Message            |
+======+====================+
| 5000 | CLI command run    |
+------+--------------------+
| 5001 | CLI command failed |
+------+--------------------+

``ldapAuth`` (6000-6999)
********************

LDAP Authentication (``ldapAuth``):

+------+--------------------------+
| Code | Message                  |
+======+==========================+
| 6000 | Ldap authentication logs |
+------+--------------------------+

``aclOps`` (7000-7999)
*****************

Access Control List Operations (``aclOps``):

+------+---------------------------+
| Code | Message                   |
+======+===========================+
| 7000 | Access control list       |
+------+---------------------------+
| 7001 | Access control list debug |
+------+---------------------------+

``certOps`` (8000-8999)
******************

Certificate Operations (``certOps``):

+------+-------------------------------+
| Code | Message                       |
+======+===============================+
| 8000 | Certificate debug             |
+------+-------------------------------+
| 8001 | Certificate being used        |
+------+-------------------------------+
| 8002 | Certificate has been verified |
+------+-------------------------------+
