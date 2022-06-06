GoAlert Ansible Role  
====================

Installs and configures [GoAlert](https://github.com/target/goalert) on any linux servers.


Role Variables
--------------

```yaml
goalert_repo_url: "https://github.com/target/goalert" # GoAlert github repo
goalert_download_url: "{{ goalert_repo_url }}/releases/download/{{ goalert_version }}/goalert-linux-amd64.tgz"
goalert_version: "v0.29.0" # Desired GoAlert version
goalert_system_user: "goalert"
goalert_system_group: "goalert"
goalert_service_state: started 
goalert_service_enabled: true # systemctl enable goalert.service
goalert_db-url: "postgres://goalert@localhost/goalert" # Database connection string (required)
goalert_args: "" # Some other GoAlert cli-options in one line (like "--api-only --http-prefix /goalert --json")
```

Example Playbook
----------------

```yaml
---
- hosts: servers
  roles:
     - { role: vandud.goalert }
```

License
-------

BSD

Author Information
------------------
[Ivan Dudin](https://github.com/vandud)
