# aws-ansible-groups-and-ec2s
This is an ansible role which:
* can create an AWS security group
* can create and spin up an ec2
* logs ssh commands for your created ec2's

Requirements
------------

* python >= 2.6 - [installation info](https://realpython.com/installing-python/)
* boto package - [installation info](https://pypi.org/project/boto/)
* AWS subnet id - *only needed for the creation of an EC2 instance*
* AMI image id - *only needed for the creation of an EC2 instance*
  
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

**Path variables**
* role_path
* key_pair_path

**EC2 instance variables**
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

**Security Group variables**
* name
* description
* vpc_id
* rules
* from_port
* to_port
* cidr_ip

Example Playbook
----------------

```yml
- hosts: localhost
  connection: local

  roles:
  - benbuzzelli.aws_ansible_groups_and_ec2s
```

Testing
-------

Run test.yml:
```
$ ansible-playbook /etc/ansible/roles/benbuzzelli.aws_ansible_groups_and_ec2s/tests/test.yml
```

Copy `--tags "tag-name"` after the above command to only complete a specified task:

tag-names:
* `create-ec2`
* `create-security-group`


look at *[my_ec2_ssh_commands.md](https://github.com/benbuzzelli/aws-ansible-groups-and-ec2s/blob/master/files/my_ec2_ssh_commands.md)* for information on how to SSH into your new instance

License
-------

BSD
