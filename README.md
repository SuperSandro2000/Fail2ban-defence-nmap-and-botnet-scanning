## Installation
Edit settings for iptables like in example-iptables file:
```
-A INPUT -p tcp -m tcp -j LOG --log-prefix "Iptables: unidentified: "
```
```
wget --no-check-certificate -O /etc/rsyslog.d/11-iptables.conf https://raw.githubusercontent.com/AndrewMarchukov/Fail2ban-defence-nmap-and-botnet-scanning/master/11-iptables.conf
wget --no-check-certificate -O /etc/fail2ban/action.d/iptables-ipset-proto6-allports.conf https://raw.githubusercontent.com/AndrewMarchukov/Fail2ban-defence-nmap-and-botnet-scanning/master/iptables-ipset-proto6-allports.conf
wget --no-check-certificate -O /etc/logrotate.d/iptables https://raw.githubusercontent.com/AndrewMarchukov/Fail2ban-defence-nmap-and-botnet-scanning/master/iptables-logrotate.d
wget --no-check-certificate -O /etc/fail2ban/filter.d/scanban-filter.conf https://raw.githubusercontent.com/AndrewMarchukov/Fail2ban-defence-nmap-and-botnet-scanning/master/scanban-filter.conf
wget --no-check-certificate -O /etc/fail2ban/jail.d/scanban-jail.conf https://raw.githubusercontent.com/AndrewMarchukov/Fail2ban-defence-nmap-and-botnet-scanning/master/scanban-jail.conf
```
and restart rsyslog, wait logs in /var/log/iptables.log then restart fail2ban