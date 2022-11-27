supertylerc.zerotier
=========

A role for installing ZeroTier on Linux and joining a ZeroTier network.

Role Variables
--------------

| Variable | Type | Purpose | Default |
|----------|------|---------|---------|
| `zerotier_download_base_url` | string | The base URL for repo URLs                                                               | `"https://download.zerotier.com"`                                                                                          |
`zerotier_gpg_key_url`         | string | The location of the GPG key for Debian-based repo URLs                                   | `"https://raw.githubusercontent.com/zerotier/ZeroTierOne/master/doc/contact%40zerotier.com.gpg"`                           |
`zerotier_apt_repository`      | string | The repository string for Debian-based installations                                     | `"deb {{ zerotier_download_base_url }}/debian/{{ ansible_distribution_release }} {{ ansible_distribution_release }} main"` |
`zerotier_network_id`          | string | The ZeroTier Network ID to join                                                          | `"8056c2e21c000001"` (the former public Earth network)                                                                     |
`zerotier_leave`               | bool   | Whether or not you wish to leave the ZeroTier network specified in `zerotier_network_id` | `false`                                                                                                                    |

Example Playbook
----------------

```yaml
---
- name: Converge
  hosts: all
  gather_facts: true
  roles:
    - name: "supertylerc.zerotier"
```

License
-------

Apache 2.0
