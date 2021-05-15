# Automate-K8s-setup
## Ansible Role to Configure K8S Multi Node Cluster over AWS Cloud.
- ec2_launch role launches instances for **Master** node with **tags** *ClusType:"k8s"*,*Node:"Master"* & **Slave** node with **tags** *ClusType:"k8s"*,*Node:"Master"*
- k8s_common,k8s_master,k8s_slave configure nodes based on this tags so 
> Use ec2 dynamic inventory 
- We need to export AWS credentials such as **Secret key** and **Access key** using "*export AWS_ACCESS_KEY_ID='YOUR_AWS_API_KEY'*" and "*export AWS_SECRET_ACCESS_KEY='YOUR_AWS_API_SECRET_KEY'*" for ec2 dynamic inventory
  - Download files for ec2 dynamic inventory *[ec2.py](https://github.com/ansible/ansible/blob/stable-2.9/contrib/inventory/ec2.py )*, *[ec2.ini](https://github.com/ansible/ansible/blob/stable-2.9/contrib/inventory/ec2.ini)*

## To setup k8s cluster
- First run **k8s_setup.yml** file using *ansible-playbook k8s_setup.yml*
- Then run **k8s_setup1.yml** file using *ansible-playbook k8s_setup1.yml*

## Blog link: https://yuktachakravarty.medium.com/automate-k8s-setup-using-ansible-over-ec2-2d141d4c0502
