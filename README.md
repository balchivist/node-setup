## Balchivist Ansible Playbooks

This repository contains the Ansible playbooks that Balchivist uses to manage the Balchivist infrastructure. These playbooks are intended to be used for running on the [dumps project on Wikimedia Cloud Services](https://wikitech.wikimedia.org/wiki/Nova_Resource:Dumps).

### Configuration

There are a few variables that needs to be changed, as they are private information and are not available in this repository. To set these configuration variables, create a new file called `settings.json` with `settings.example.json` as a template. The variables, along with their explanations, are as follows:

- `balchivist_directory_user`: The Unix username that will own the temporary directory `/srv/temp`
- `balchivist_directory_group`: The Unix group name of the user that will own the temporary directory `/srv/temp`
- `mariadb_client_host`: The hostname to the database server, for MariaDB to automatically connect to when using `mysql`.
- `mariadb_client_user`: The username to access the MariaDB database server.
- `mariadb_client_password`: The password for the user to access the MariaDB database server.
- `legacycron_email_address`: The email address to use for sending cron emails to.

The list of servers are defined in `production`, and are categorized into `runners` (Balchivist runners) and `webservers` (Balchivist web servers).

### Running the playbooks

The playbooks utilizes [Ansible](https://docs.ansible.com/ansible/latest/index.html) to run the tasks. The `ansible-playbook` command is used to run the playbooks. To run the playbooks, run the following command:

```
ansible-playbook -i production site.yml
```

All command parameters are available in the Ansible documentation.
