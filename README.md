# aws-ansible-groups-and-ec2s
This is an ansible role which:
* can create an AWS security group
* can create and spin up an ec2
* logs your created ec2 ssh commands

Requirements
------------

  1. boto package - [installation info](https://pypi.org/project/boto/)
  
Installation
------------

Using `ansible-galaxy`:
```
$ ansible-galaxy install benbuzzelli.aws_ansible_groups_and_ec2s
```

Using `git`:
```
$ git clone https://github.com/benbuzzelli/aws-ansible-groups-and-ec2s.git
```

Role Variables
--------------

Path variables
* role_path
* key_pair_path

EC2 instance variables
* key_name
* region
* instance_type
* image
* Name
* Owner
* monitoring
* vpc_subnet_id
* assign_public_ip
* group

Security Group variables
* name
* description
* vpc_id
* rules
* from_port
* to_port
* cidr_ip

Example Playbook
----------------

```
- hosts: localhost
  connection: local

  roles:
  - aws
```

Testing
-------

Create only an ec2 instance:
```
$ ansible-playbook path/test.yml --tags create-ec2
```

License
-------

BSD
