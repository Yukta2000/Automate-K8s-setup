ec2_launch
=========


  -  ec2_launch role launches instances for Master node with tags ClusType:"k8s",Node:"Master" & Slave node with tags ClusType:"k8s",Node:"Master"
  -  k8s_common,k8s_master,k8s_slave configure nodes based on this tags so


Requirements
------------
We need to export AWS credentials such as Secret key and Access key using "export AWS_ACCESS_KEY_ID='YOUR_AWS_API_KEY'" and "export AWS_SECRET_ACCESS_KEY='YOUR_AWS_API_SECRET_KEY'" for ec2 dynamic inventory

### Download files for ec2 dynamic inventory ec2.py, ec2.ini

