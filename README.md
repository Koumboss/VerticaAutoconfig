# VerticaAutoconfig
Small Ansible script for automatically configuring OS level prerequisites on all VMs before installation.

## Before running the script
1. In order to run the script, it is essential to have Ansible installed, to have a root account and to install the Vertica RPM and to drop it in a dedicated path.
2. Install Python and its command line tool pip3
3. Install Ansible using pip3

## How to run
1. Download the project from Github
2. Modify the inventory.ini file with your one servers’ IPs
3. Modify the vars.yml file appropriately :
```
[myhosts]
10.30.30.149
10.30.30.150
10.30.30.146
10.30.30.147
10.30.30.148
10.30.30.24
```
4. Run the following command to execute the script :
```
ansible-playbook -i inventory.ini vertica_prereq.yml
```

# Next steps
1. Automatically generate a backup.ini file for backups.
2. Automatically create the DB based on a configuration file.
