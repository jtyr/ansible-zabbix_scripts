zabbix_scripts
==============

Ansible role which helps to install Alert and External scripts for Zabbix
Server and Proxy.

The configuration of the role is done in such way that it should not be
necessary to change the role for any kind of configuration. All can be
done either by changing role parameters or by declaring completely new
configuration as a variable. That makes this role absolutely
universal. See the examples below for more details.

Please report any issues or send PR.


Usage
-----

```
- name: Example of how to deploy Alert script for Slack
  hosts: machine1
  vars:
    # Make the Slack script to be installed
    zabbix_scripts_alertscripts:
      - slack.sh

    # Configure the Slack URL
    zabbix_scripts_slack_url: https://hooks.slack.com/services/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

    # Customize emojis
    zabbix_scripts_slack_emoji_recovery: ":rock_on:"
    zabbix_scripts_slack_emoji_problem: ":scream:"
    zabbix_scripts_slack_emoji_other: ":zabbix:"

    # Customize the message format
    zabbix_scripts_slack_message: "${emoji} - ${subject}: $3"
  roles:
    - zabbix_proxy
    - zabbix_scripts
```


Role variables
--------------

```
```


Dependencies
------------

- [`zabbix_proxy`](https://github.com/jtyr/ansible-zabbix_proxy) (optional)
- [`zabbix_server`](https://github.com/jtyr/ansible-zabbix_server) (optional)


License
-------

MIT


Author
------

Jiri Tyr
