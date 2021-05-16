ec2_launch
=========


  -  ec2_launch role launches instances for Master node with tags ClusType:"k8s",Node:"Master" & Slave node with tags ClusType:"k8s",Node:"Master"
  -  k8s_common,k8s_master,k8s_slave configure nodes based on this tags so


Requirements
------------
We need to export AWS credentials such as Secret key and Access key using "export AWS_ACCESS_KEY_ID='YOUR_AWS_API_KEY'" and "export AWS_SECRET_ACCESS_KEY='YOUR_AWS_API_SECRET_KEY'" for ec2 dynamic inventory

### Download files for ec2 dynamic inventory ec2.py, ec2.ini

**Sample Playbook**
- hosts: localhost
  vars_prompt:
    - name: AWS_REGION
      prompt: "Enter region:"
      private: no
      default: "us-east-1"
    - name: AWS_MASTER_KEY_FILE
      prompt: "Enter name of Master node SSH Key file:"
      private: no
    - name: AWS_SLAVE_KEY_FILE
      prompt: "Enter name of  Slave node SSH Key file:"
      private: no
    - name: AWS_Image_ID
      prompt: "Enter AMI ID of AMAZON LINUX IMAGE:"
      private: no
    - name: AWS_SUBNET_ID
      prompt: "Enter SUBNET ID:"
      private: no
    - name: AWS_SECURITY_GROUP_NAME
      prompt: "Enter Security Group Name:"
      private: no
    - name: MASTER_COUNT
      prompt: "How many master nodes?"
      private: no
    - name: SLAVE_COUNT
      prompt: "How many slave nodes?"
      private: no
       
  roles:
  - role: "ec2_launch"





