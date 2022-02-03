# What is Ansible
Ansible is a configuration management tool.
# What are the Advantages of Ansible?
- Agentless, it doesn’t require any extra package/daemons to be installed
    Linux it uses ssh
    windows it uses winrm
- Very low overhead
- Good performance
- Idempotent
- Declarative

# What are the Pros and Cons of Ansible? 
Pros: 1. Open Source 2. Agent less 3. Improved efficiency , reduce cost 4. Less Maintenance 5. Easy to understand yaml files 
Cons: 1. Underdeveloped GUI with limited features 2. Increased focus on orchestration over configuration management 3. SSH communication slows down in scaled environments

# what’s the difference between Ansible Playbook and Roles?

Roles | Playbooks
:-- | :--
Roles are reusable subsets of a play. | Playbooks contain Plays. 
A set of tasks for accomplishing certain role. | Maps among hosts and roles.
Example: common, webservers. | Example: site.yml, fooservers.yml, webservers.yml

# How do I see a list of all the ansible_ variables ?
Ansible by default gathers “facts” about the machines, and these facts can be accessed in Playbooks and in templates. To see a list of all the facts that are available about a machine, you can run the “setup” module as an ad-hoc action: 
`Ansible -m setup hostname` 
This will print out a dictionary of all the facts that are available for that particular host.

# How to execute some errand (or) play on localhost just while executing playbooks on various has on an ansible? 
In ansible, there is a module called delegate_to, in this module area give the specific host (or) has where your errands (or) assignment should be run. undertakings: name: ” Elasticsearch Hitting” uri: url=’_search?q=status:new’ headers='{“Content-type”:”application/json”}’ method=GET return_content=yes register: yield delegate_to: 127.0.0.1

