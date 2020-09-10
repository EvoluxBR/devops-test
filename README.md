# Telecom Carrier, the infrastructure project.

A cloud telecom carrier needs a way to manage and provide a provisioned and installed telephony stack.

Prepared with ❤️ by [Evolux Sistemas](https://www.evolux.net.br/) team.

### Briefing

The basic user story is:

> As a member of Ops team I need a way to get the telephony stack ready to join the cluster

From an engineering perspective, consider this is an automated task.
Ops users need to be safe safely run this without any expertise with the telephony
platform  (in our case, [FreeSWITCH](https://freeswitch.com/)).

The rest of your team is dealing with other tasks, So you're the one in charge
of making an automated [Ansible playbook](https://docs.ansible.com/ansible/latest/user_guide/playbooks.html)
to do the job.

That said, you team had agreed with these acceptance criteria:

- It needs to orchestrated by an Ansible playbook;
- Should be compatible with GNU/Linux, precisely with both Debian Strech and Buster;
- FreeSWITCH must be installed from source (https://github.com/signalwire/freeswitch);
- The FreeSWITCH instance must be managed by the Systemd;
- 3 [Sofia](https://freeswitch.org/confluence/display/FREESWITCH/Sofia+SIP+Stack) profiles must be UP and Running:
  - Internal at port 5060,
  - External at port 5080,
  - VPN at port 5090;
- And Ops members must be able to access the `fs_cli` externally.

### Extra features

Nobody is expecting it. 💅 But it will be nice to see any of these things:

- `fs_cli` protected by a network ACL;
- all passwords and ACLs being handled by the `host_vars` in a safe way.

Just don't overengineer it too much. Keep it simple. And don't try to rob product management role!

### Points of interest

It all depends of the level of seniority you're applying to, of course. But our main observations are:

- general computing and linux knowledge;
- your networking and security knowledge;
- Ansible developer experience details like:
  - default tasks knowledge;
  - `host_vars` handling;
  - inventory (how do you to manage hosts and groups);
  - task idempotency;
  - usage of Ansible facts;
  - playbook portability;
  - self explanatory playbook (is it easy to read and understand?);
  - secrets management.

Be cool and happy coding!
