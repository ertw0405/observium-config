# observium-config
Observium on CentOS 7
Details installation step refer to [here](http://docs.observium.org/install_rhel7/)

Install snmpd on servers that need to be monitored
```
sudo yum -y install net-snmp net-snmp-utils
sudo mv /etc/snmp/snmpd.conf /etc/snmp/snmpd.conf.orig
sudo vim /etc/snmp/snmpd.conf
```
For the snmpd.conf 
```
com2sec readonly _observium_host_ip_ _snmp_community_name_
group MyROGroup v1 readonly
group MyROGroup v2c readonly
group MyROGroup usm readonly
view all included .1 80
access MyROGroup "" any noauth exact all none none
syslocation "Taiwan, Asia"
syscontact user@your-domain.com
```
Then restart the setup auto-start for snmpd
```
sudo service snmpd restart
sudo chkconfig snmpd on
```
