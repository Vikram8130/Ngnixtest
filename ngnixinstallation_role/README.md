#### All the information is mentioned below for the ngnixinstallation_role that I have tried to created.

1. /etc/ansible/roles/ngnixinstallation_role/tasks/main.yml:

Here, I have define a handful of tasks that update the operating system, install an Nginx web server, and set up a minimal custom configuration

2. /etc/ansible/roles/ngnixinstallation_role/defaults/main.yml:-

Here I have set default values for the variables used in the tasks. If there is no other definition for these variables, they will be picked up and used by the role, but usually, they are meant to be easily overwritten.

3. /etc/ansible/roles/ngnixinstallation_role/vars/main.yml:-

Here I have defined values with higher precedence that aren’t meant to be overridden at the playbook level. Here, we override the default variable that defines the Nginx custom directory.

4. /etc/ansible/roles/ngnixinstallation_role/handlers/main.yml:-

In this handlers directory, I have defined a handler that will be triggered to Start the Nginx service.

5. /etc/ansible/roles/ngnixinstallation_role/templates/nginx.conf.j2:-

In this templates directory, I have tried to leverage a Jinja2 template file for the Nginx configuration that gets the Nginx custom directory value from one of our previously defined variables.

6. /etc/ansible/roles/ngnixinstallation_role/files/index.html:-

In the files directory, I have defined a static file index.html that will serve as our static demo webpage.

7. /etc/ansible/roles/ngnixinstallation_role/meta/main.yml:-

Here I have used the meta directory to add metadata and information about the role. Any role dependencies by other roles go here as well.
