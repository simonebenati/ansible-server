# ansible-server
My way of provisioning debian servers


Notes: at the moment the repository doesn't utilize roles due to the scale of my "home" infrastructure.
But if things got bigger instead of using a single playbook file that contains tags i.e. [web_servers] = 192.168.1.14
We could make a folder called 'roles' that would contain other folders called with the previous tag name so for example (those represent our roles): 

$ls ~/ansible_server/roles would output:
web_servers  file_servers

And so on..

For each role directory we'll create another directory and will call it 'tasks'.

Inside tasks will reside our role specific playbook that contains specific code for specific machines in order to better mantain it, update it and understand it. So to avoid a huge file with lots of line hard to read and update.

We will keep at the root of the directory one .yml file that contains all the roles aforementioned so that, ansible will know against which machines to run each role-specific playbook

More on: https://docs.ansible.com/ansible/2.9/user_guide/playbooks_reuse_roles.html