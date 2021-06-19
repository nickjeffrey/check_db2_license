# check_db2_license
nagios check for IBM DB2 database license status

# Requirements
perl, ssh

# Configuration
It is assumed you already have working SSH key pair authentication between the nagios server and the monitored host.

Add a section similar to the following to the services.cfg file on the nagios server.
```
define service {
        use                             generic-24x7-service
        host_name                       db2server01
        service_description             DB2 license status
        normal_check_interval           1440         ; Check the service every 1440 minutes (once per day) under normal conditions
        check_command                   check_by_ssh!"/usr/local/nagios/libexec/check_db2_license /path/to/db2licm"
        }
```

