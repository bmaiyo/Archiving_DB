# Archiving Old Tables in Database
This is a simple project for Archiving Old Tables in Database.
# Design Principles
- The Project is implemented using Ansible written in YAML language.
- The Playbook has incorporated afew Ansible modules including: vars, find, debug, s3, file and s3_event.
- Variables have been defined seperately on the and called on the code.
# Running the Project
- The project is run using the playbook file i.e main_playbook.yml
```
ansible-playbook -i /etc/hosts/database_hosts main_playbook.yml
```
- The project checks for the RDS MySQL archive files on the local path specified in the vars.yml file i.e /var/logs/
- Prints the output of this.
- The project then backs-up the data in this folder to the s3 bucket on our AWS account.
```
i.e we use the s3 sync module for this: aws s3 sync /path/to/files s3://s3bucket
```
- This is then followed by deleting the files from the folder.
- An email is sent on success of the whole process.
```
Use of SNS ansible module to send email incoporating the 'when' module: "when: delete_complete|succeeded"
```
- A notificaton on email should also be received incase of failure using the SNS module as well.
# API Reference
- http://docs.ansible.com/ansible/latest/index.html


