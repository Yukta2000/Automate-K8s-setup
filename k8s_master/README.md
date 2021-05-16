k8s_master
========
It will do remaining configurations only for master

Requirements
------------
We need to export AWS credentials such as Secret key and Access key using "export AWS_ACCESS_KEY_ID='YOUR_AWS_API_KEY'" and "export AWS_SECRET_ACCESS_KEY='YOUR_AWS_API_SECRET_KEY'" for ec2 dynamic inventory

## Download files for ec2 dynamic inventory ec2.py, ec2.ini

**Run k8s_common role before using this role to do configurations needed before using this role**

**Sample Playbook**
#Common setup
- hosts: tag_Node_Master
  vars_prompt:
    - name: SSH_KEY_PATH
      prompt: "Enter path of SSH KEY for master"
      private: no
  roles:
  - role: "k8s_common"

- hosts: tag_Node_Slave
  vars_prompt:
    - name: SSH_KEY_PATH
      prompt: "Enter path of SSH KEY for slave"
      private: no
  roles:
  - role: "k8s_common"

#Master configuration
- hosts: tag_Node_Master
  vars_prompt:
    - name: SSH_KEY_PATH
      prompt: "Enter path of SSH KEY for master"
      private: no
  roles:
  - role: "k8s_master"

#Slave configuration
- hosts: tag_Node_Slave
  vars_prompt:
    - name: SSH_KEY_PATH
      prompt: "Enter path of SSH KEY for slave"
      private: no
  roles:
  - role: "k8s_slave"

#Checking if nodes connected
- hosts: tag_Node_Master
  vars_prompt:
    - name: SSH_KEY_PATH
      prompt: "Enter path of SSH KEY for master"
      private: no
  vars:
    - ansible_user: ec2-user
    - ansible_ssh_private_key_file: "{{ SSH_KEY_PATH }}"
    - ansible_become: true
  tasks:
    - name: "Checking nodes"
      command: "kubectl get nodes"
      register: nodes
    - debug:
        msg: "{{ nodes.stdout_lines }}"
          



