# interworx-fail2ban
Rules for Fail2Ban that I use for Interworx Control Panel

To install fail2ban:
```
 yum install fail2ban
 chkconfig fail2ban on
```
place jail.local in /etc/fail2ban folder

copy filter.d/qmail* rules into /etc/fail2ban/filter.d/

restart fail2ban:
```
service fail2ban restart
```

or cent os 7
```
systemctl fail2ban restart
```

to see rules in action:
```
fail2ban-client status
```

to see particular rule:
```
fail2ban-client status <jail>
```
for example:
```
fail2ban-client status qmail-smtpusername
```  
to see all rules at once:
```
fail2ban-client status | sed -n 's/,//g;s/.*Jail list://p' | xargs -n1 fail2ban-client status
```

