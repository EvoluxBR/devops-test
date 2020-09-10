# Telecom Carrier, the infrastructure project.

A cloud telecom carrier needs a way to manage and provide a telephony stack provisioned and installed.

Prepared with ❤️  by [Evolux Sistemas](https://www.evolux.net.br/) team.

### Briefing

The basic user story is:

> As a member of OPS team I need a way to get the telephony stack ready to join the cluster

From an engineering perspective, consider this is an automated task that needs to be safe to be
executed by anyone without any expertise with FreeSWITCH.

So you're the one in charge of making an automated ansible playbook to do the job.

That said, here are the task acceptance criteria:

- This needs to managed by an Ansible playbook
- Should be compatible with Linux, more precisely with both Debian Strech and Buster
- FreeSWITCH must be installed from source (https://github.com/signalwire/freeswitch)
- The FreeSWITCH instance must be managed by the Systemd
- 3 Sofia profiles must be UP and Running
  - Internal - port 5060
  - External - port 5080
  - VPN - 5090
- The OPS members would be able to access the fs_cli externally

### Extra features

Nobody is expecting it.💅 But it will be nice to see any of these things:

- The fs_cli must be protected by a network ACL
- All passwords and ACLs must be handled by the host_vars in a safe way

Just don't overengineer it too much. Keep it simple. And don't try to rob product management role!

### Points of interest

It all depends of the level of seniority you're applying to, of course. But our main observations are:

- general computing and linux knowledge;
- your networking and security knowledge;
- ansible developer experience details like:
  - default tasks knowledge;
  - host_vars handling;
  - inventory - how do you to manage hosts and groups;
  - task idempotency;
  - usage of ansible facts;
  - playbook portability;
  - self explanatory playbook, is it easy to read and understand?;
  - secrets management;


Be cool and happy coding!
