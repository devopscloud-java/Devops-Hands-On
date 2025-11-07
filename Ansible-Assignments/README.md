🧩 Setup Overview

We’ll create:

1 Master Node (Controller) — runs Ansible

2 Slave Nodes (Managed Hosts)

slave1 → install Java

slave2 → install MySQL

1️⃣ Inventory File (inventory.ini)

This file defines your Ansible hosts.

[all:vars]
'''
ansible_user=ubuntu
ansible_ssh_private_key_file=~/.ssh/id_rsa

[slave1]
slave1 ansible_host=192.168.1.10

[slave2]
slave2 ansible_host=192.168.1.11
'''

⚙️ Replace IPs and SSH key path with your actual setup.

2️⃣ Playbook: setup_cluster.yml

Here we define two plays — one for each node.

'''
---
- name: Install Java on Slave1
  hosts: slave1
  become: yes
  tasks:
    - name: Update apt cache
      apt:
        update_cache: yes

    - name: Install Java (OpenJDK 11)
      apt:
        name: openjdk-11-jdk
        state: present

    - name: Verify Java installation
      command: java -version
      register: java_version
      ignore_errors: yes

    - debug:
        var: java_version.stdout_lines

- name: Install MySQL on Slave2
  hosts: slave2
  become: yes
  tasks:
    - name: Update apt cache
      apt:
        update_cache: yes

    - name: Install MySQL Server
      apt:
        name: mysql-server
        state: present

    - name: Ensure MySQL is running
      service:
        name: mysql
        state: started
        enabled: yes

    - name: Check MySQL version
      command: mysql --version
      register: mysql_version
      ignore_errors: yes

    - debug:
        var: mysql_version.stdout_lines
      
      '''

3️⃣ Run the Playbook
ansible-playbook -i inventory.ini setup_cluster.yml

4️⃣ Verify

On the controller node:

ansible slave1 -m command -a "java -version" -i inventory.ini
ansible slave2 -m command -a "mysql --version" -i inventory.ini


You should see Java and MySQL versions returned.

✅ Expected Outcome
Node	Task	Result
slave1	Install Java	Java 11 installed and active
slave2	Install MySQL	MySQL server running
