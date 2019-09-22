# Ansible Workshop AWS Environment

This is an Ansible playbook that provisions an environment on AWS for doing the [ansible-workshop](https://github.com/avishayil/ansible-workshop).

### Pre-requisites

- Provision an EC2 instance on a **public subnet** (with public ip association) using the AWS console and create a new KeyPair (MyKeyPair). Make sure the KeyPair is saved with the same name as it appears on the AWS Console (**MyKeyPair** on the AWS console should be named **MyKeyPair.pem** on your computer).
- Download the KeyPair to your computer.
- SSH to this EC2 instance and install Ansible using `sudo pip install ansible pywinrm[credssp] requests-credssp --ignore-installed` 
- Clone this repository `git clone https://github.com/avishayil/ansible-workshop-aws-env` to the machine.
- Copy (or SCP) the KeyPair from your computer to the same folder as the cloned repository.
- Fill the correct variables inside the file `host_vars/localhost` regarding your AWS environment
- Alter the `playbook.yml` file and change this line: `loop: "{{ query('sequence', 'start=1 end=20') }}"` according to the number of environment required.

### Running the Playbook

````
ansible-playbook playbook.yml -e "ansible_password=nopass"
````
