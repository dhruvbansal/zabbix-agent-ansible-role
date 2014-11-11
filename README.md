This is an [Ansible](http://www.ansible.com/home) role for installing
[Zabbix agent](https://www.zabbix.com/documentation/2.0/manual/concepts/agent).

The following variables are exposed for configuration

* `zabbix_server_host` -- IP address of the Zabbix server the Zabbix agent will accept connections from (also applied for active agents)
* `zabbix_agent_enable_remote_commands` -- set to `1` to allow Zabbix agent to evaluate remote commands sent from Zabbix server
* `zabbix_agent_unsafe_user_parameters` -- set to `1` to allow Zabbix agent to evaluate "unsafe" user parameters
* `zabbix_user_parameters` -- list of user parameters, e.g -
```
zabbix_user_parameters:
  - key: ping[*]
    command: ping $1
  - key: ls[*]
    command: ls $1
```
* `zabbix_agent_hostname` -- override the default hostname picked up by the Zabbix agent
* `zabbix_agent_metadata` -- optional metadata used during host registration
* `zabbix_agent_metadata_item` -- optional item to obtain metadata used during host registration

A logstash input file is also defined for the nginx logs created by
the virtual server.
