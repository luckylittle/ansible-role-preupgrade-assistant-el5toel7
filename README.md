ansible-role-preupgrade-assistant-el5toel7
=========

This role helps you to run `preupg` tool on many different machines and gather the results in one place (ideally the Apache server running on the Ansible control host itself). Then you will be able to see all the results at this URL: `http://<ip_address>/preupg-<HOSTNAME>.html`:

| Exit code | Explanation |
|-----------|-------------|
| PASS | Everything is fine. You should be able to proceed to the migration when all exit codes are listed as PASS. |
| FAIL | Extreme migration risks. Migration is not possible. |
| NEEDS_ACTION | High migration risk. Some administrator action is needed before running the migration. |
| NEEDS_INSPECTION | Lower or medium risks. This exit code does not necessarily mean the migration will fail, but it might result in a system that is not fully functional. Some parts of the system need to be checked and, if needed, fixed by the administrator. |
| FIXED | Changes required for the migration were fixed automatically. You do not need to review them further. |
| INFORMATIONAL | Useful, but not critical, information. |
| NOT_APPLICABLE | The package you asked to test is not on your system. |
| ERROR | This usually indicates errors in the tools themselves. Report this type of problem to Red Hat Support. |

_Migrations require some level of review by a system administrator as it is impossible to predict all of the ways a system might be uniquely configured or modified._

Requirements
------------

Because RHEL5 is very old and has very old Python, you will only be able to use Ansible v2.3 or older. The role itself does not have any dependencies, other than Ansible & Python. The `preupg` tool on RHEL 5.11 has the following dependencies:

- preupgrade-assistant 2.3.1-2.el5_11
- preupgrade-assistant-el5toel7-data 0.20170209-1.el5_11
- libxslt 1.1.17-4.el5_8.3
- openscap 1.0.8-1.el5_10
- openscap-engine-sce 1.0.8-1.el5_10
- openscap-utils 1.0.8-1.el5_10
- preupgrade-assistant-el5toel7 0.6.47-3.el5_11

Role Variables
--------------

No variables.

Dependencies
------------

No dependencies.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

```text
- hosts: rhel5_servers
  roles:
      - ansible-role-preupgrade-assistant-el5toel7
```

License
-------

MIT

Author Information
------------------

[@luckylittle](https://github.com/luckylittle)
