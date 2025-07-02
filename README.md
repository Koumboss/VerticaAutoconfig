# VerticaAutoconfig
Small Ansible script for automatically configuring OS level prerequisites on all VMs before installation.

## Before running the script
1. Make sure to use the root user and that passwordless ssh is enabled. Otherwise, run the following command from your initiator server towards all Vertica nodes :
```
# Replace the IP with each IP of your cluster
ssh-copy-id 10.30.30.23
```
2.  In order to run the script, it is essential to have Ansible installed, to have a root account and to install the Vertica RPM and to drop it in a dedicated path.
3. Install Python and its command line tool pip3
```
yum install -y python39
```
4. Install Ansible using pip3
```
pip3 install ansible
```

## How to run
1. Download the project from Github
![image](https://github.com/user-attachments/assets/b602ec9e-90f9-4ac7-b31d-5c5c4d7d9cf5)
2. Modify the inventory.ini file with your one servers’ IPs :</br>
![image](https://github.com/user-attachments/assets/f6b91c7e-6b8f-4f3a-81a8-3f6f5db4a57b)
3. Modify the vars.yml file appropriately :</br>
![image](https://github.com/user-attachments/assets/55deed8b-0552-4a82-85bb-b40cd8b1690b)
4. Run the following command to execute the script :
```
ansible-playbook -i inventory.ini vertica_prereq.yml
```
![image](https://github.com/user-attachments/assets/e62cdbce-c723-4f77-8665-5e0c0f3b7736)
![image](https://github.com/user-attachments/assets/f44674b6-f99e-4fd4-a802-c4394f08ba82)
5. You can finally rerun the install_vertica script and your prerequisites will automatically pass.
![image](https://github.com/user-attachments/assets/81923704-1493-4e8b-b396-9f3b7f45c70e)


# Next steps
1. Automatically generate a backup.ini file for backups.
2. Automatically create the DB based on a configuration file.
