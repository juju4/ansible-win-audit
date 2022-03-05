[![Appveyor - Master](https://ci.appveyor.com/api/projects/status/y6thcpaynaf2t9i3?svg=true)](https://ci.appveyor.com/project/juju4/ansible-win-audit)
![Appveyor - Devel](https://ci.appveyor.com/api/projects/status/y6thcpaynaf2t9i3/branch/devel?svg=true)

# Windows audit ansible role

Ansible role to setup audit on windows system.

## Requirements & Dependencies

### Ansible
It was tested on the following versions:
 * 2.3 (Not working! [ansible#23940](https://github.com/ansible/ansible/issues/23940) = template upload failing)
 * 2.4
 * 2.5b2

### Operating systems

Tested in Appveyor

## Example Playbook

Just include this role in your list.
For example

```
- host: all
  roles:
    - juju4.win-audit
```

Run
```
$ ansible -i inventory -m win_ping win --ask-pass
$ ansible-playbook -i inventory --limit win site.yml
```

## Variables

See defaults/main.yml for full scope

## Continuous integration

This role has a travis basic test (for github, syntax check only), Appveyor test and a Vagrantfile (test/vagrant).

```
$ cd /path/to/roles/juju4.win-audit/test/vagrant
$ vagrant up
$ vagrant provision
$ vagrant destroy
$ ansible -i .vagrant/provisioners/ansible/inventory/vagrant_ansible_inventory -m win_ping -e ansible_winrm_server_cert_validation=ignore -e ansible_ssh_port=55986 all
```

## Troubleshooting & Known issues

## FAQ

Reference links
* https://posts.specterops.io/hunting-with-active-directory-replication-metadata-1dab2f681b19
* https://social.technet.microsoft.com/wiki/contents/articles/25946.metadata-de-replication-et-analyse-forensic-active-directory-fr-fr.aspx

## License

BSD 2-clause
