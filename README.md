# Archiving Old Tables in Database
This is a simple project for Archiving Old Tables in Database.
# Design Principles
- The Project is implemented using Ansible written in YAML language.
- The Playbook has incorporated afew Ansible modules including: vars, find, debug, s3, file and s3_event.
- Variables have been defined seperately on the and called on the code.
# Running the Project
- The project is run using the playbook file i.e main_playbook.yml
- The project checks for the RDS MySQL archive files on the local path specified in the vars.yml file i.e /var/logs/
- Prints the output of this.
- The project then backs-up the data in this folder to the s3 bucket on our AWS account.
- This is then followed by deleting the files from the folder.
- An email is sent on success of the whole process.
- A notificaton on email should also be received incase of failure.
