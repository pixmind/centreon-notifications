centreon-notifications
=================

## Setup

1. Activate autologin in Centreon Web UI : [Centreon Blog](https://blog.centreon.com/autologin-to-centreon-web-interface/)
2. Download the scripts in the plugins directory and modify these following variables :
    * $url : URL of the Centreon Web UI ( eg. https://centreon.foo.bar:8081 )
    * $from : from email address desired
    * $user : Centreon's login user
    * $token : Token for autologin
3. Make the files executable.
4. On distributed platform, don't miss to install php on your pollers
6. Change the command line for host-notify-by-email and service-notify-by-email notification's command :
    * `$USER1$/host_email "$NOTIFICATIONTYPE$" "$HOSTNAME$" "$HOSTALIAS$" "$HOSTSTATE$" "$HOSTADDRESS$" "$HOSTOUTPUT$" "$LONGDATETIME$" "$SERVICEDESC$" "$SERVICESTATE$" "$CONTACTEMAIL$" "$TOTALHOSTSUP$" "$TOTALHOSTSDOWN$" "$HOSTACKAUTHOR$" "$HOSTACKCOMMENT$"`
    * `$USER1$/service_email "$NOTIFICATIONTYPE$" "$HOSTNAME$" "$HOSTALIAS$" "$HOSTSTATE$" "$HOSTADDRESS$" "$SERVICEOUTPUT$" "$LONGDATETIME$" "$SERVICEDESC$" "$SERVICESTATE$" "$CONTACTEMAIL$" "$SERVICEDURATIONSEC$" "$SERVICEEXECUTIONTIME$" "$TOTALSERVICESWARNING$" "$TOTALSERVICESCRITICAL$" "$TOTALSERVICESUNKNOWN$" "$LASTSERVICEOK$" "$LASTSERVICEWARNING$" "$SERVICENOTIFICATIONNUMBER$" "$SERVICEACKAUTHOR$" "$SERVICEACKCOMMENT$"`
7. Generate, move and export the new configuration on your all pollers

## Screenshots
![host.png](https://raw.githubusercontent.com/seancdugan/nagios-notifications/master/host.png)
![service.png](https://raw.githubusercontent.com/seancdugan/nagios-notifications/master/service.png)

## Credits
* nagios-notifications were originally written by seancdugan at https://github.com/seancdugan/nagios-notifications and I made some of my own changes to adapt to Centreon.

* host_email and service_email were originally written by shawnbrito at http://exchange.nagios.org/directory/Addons/Notifications/Send-HTML-Alert-Email-v2/details and I made some of my own tweaks to better suit my needs.