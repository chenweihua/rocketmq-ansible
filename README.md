RocketMQ Ansible
=========

Requirements
------------
- download `apache-rocketmq-all.tar.gz` bin file in files folder
- install jdk and set JAVA_HOME: /usr/lib/jvm/java

Role Variables
--------------

Node's role specified by variable: `rocket_type` that would be one of: _broker_ , _nameserver_

Example Playbook
----------------
examples for nameserver and broker

  ```yml
    - hosts: servers
      vars:
        - rocketmq_nameserver_list: 192.168.19.13:9876;192.168.19.14:9876
      roles:
        - {role: "rocketmq-ansible", rocket_type: "nameserver"}
        - {role: "rocketmq-ansible", rocket_type: "broker",
            rocketmq_broker_name: "brokerB",
            rocketmq_broker_id: 3,
            rocketmq_role: ASYNC_MASTER
            }
        - {role: "rocketmq-ansible", rocket_type: "broker",
            rocketmq_broker_name: "brokerB",
            rocketmq_broker_id: 4,
            rocketmq_role: SLAVE
            }
  ```

License
-------

MIT

Author Information
------------------

Zhai Zhijun from [showme.codes](https://showme.codes)