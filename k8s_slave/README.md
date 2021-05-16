k8s_slave
=========
It will do remaining configurations only for slave

## Requirements

We need to export AWS credentials such as Secret key and Access key using "export AWS_ACCESS_KEY_ID='YOUR_AWS_API_KEY'" and "export AWS_SECRET_ACCESS_KEY='YOUR_AWS_API_SECRET_KEY'" for ec2 dynamic inventory
## Download files for ec2 dynamic inventory ec2.py, ec2.ini

**Run k8s_common role before using this role to do configurations needed before using this role**
**Also master_token fact must be available in master node**

Sample Playbook: k8s_setup1.yml at https://github.com/Yukta2000/Automate-K8s-setup
