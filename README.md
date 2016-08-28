# **Deep Security Scripts**

Scripts written in pyhton to execute some actions through the DSM APIs. The goal is to help how to use scripts to make the administration of Deep Security solution even easier.

## **Dependencies**

A unified python SDK for the Trend Micro Deep Security APIs http://trendmicro.com/deepsecurity

https://github.com/deep-security/deep-security-py

## **Version**

1.0

## **Deep Seuciryt Manager Tested Version**

9.6

# **Usage**

git clone https://github.com/ari-neto/tmds.git
git submodule init

The script will list some informations about the DS Client:
* Computer_ID
* Computer Name
* Recommend Rules
* Overall Status
* Overal Version
* Overall Anti Malware Status
* Overall Anti Firewall Status
* Overall Anti IPS Status
* Overall Web Reputation Status
* Overall Log Inspection Status

And will execute this actions:
* clear_alerts_and_warnings
* send_events 

The filter used in the script is to list informatons with DSA 9.x clients, you could use the script to be executed to a specific client to do it you need to change "overall_versio"='9.*|8.*'" to "name='<computer name>'.

Change
  ~~~
    for computer_id in mgr.computers.find(overall_version='9.*|8.*'):
  ~~~
 to
 ~~~
    for computer_id in mgr.computers.find(name='<computer name>'):
 ~~~

You should to define your credenditals with API Access in the script (ds_script.py line 6), to enable API Access:

hostname=<your DSM IP or DSM FQDN>
username=<DSM Username with API Access>
password=<DSM Username password>

[API_Access](https://github.com/ari-neto/tmds/blob/master/images/api_access.png)