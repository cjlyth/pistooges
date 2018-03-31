## Host info
```bash
# b8:27:eb:8a:9e:70
10.1.10.210 larry larry.cjlyth.net

# b8:27:eb:2d:27:92
10.1.10.192 curly curly.cjlyth.net

# b8:27:eb:e1:f9:de
10.1.10.76 mo mo.cjlyth.net
```

## Steps followed

May need 
```bash
export ANSIBLE_HOST_KEY_CHECKING=False
```

Added the following to `/etc/ansible/hosts`

```bash
[pistooges]
larry.cjlyth.net
curly.cjlyth.net
mo.cjlyth.net
```

Added the following to ~/.ssh/config

```bash
Host *.cjlyth.net
  User pi
```

Then this command should work

```bash
ansible all -m ping
ansible all -a "/bin/echo hello"

ansible all -a "/bin/cat /proc/device-tree/model"
```

```bash
ansible-playbook playbooks/ping.yml
ansible-playbook playbooks/setup.yml
ansible-playbook playbooks/update.yml
```

