# Ansible deploy utilities for RESTBase and others

You'll need Ansible 1.8+. Debian currently only provides 1.7, so you'll need
to install from [the
PPA](http://docs.ansible.com/intro_installation.html#latest-releases-via-apt-ubuntu), [pip, git or the tarball](http://docs.ansible.com/intro_installation.html).

Examples:

Test:
```bash
ansible-playbook -i staging roles/restbase/deploy.yml --check
```
To run this for real:
```bash
ansible-playbook -i staging roles/restbase/deploy.yml

PLAY [restbase]
*************************************************************** 

TASK: [check out the deploy repo]
********************************************* 
changed: [cerium.eqiad.wmnet]

TASK: [restart restbase]
****************************************************** 
changed: [cerium.eqiad.wmnet]

TASK: [check port 7231]
******************************************************* 
ok: [cerium.eqiad.wmnet]

TASK: [wait 10s for LVS]
****************************************************** 
ok: [cerium.eqiad.wmnet]

TASK: [check out the deploy repo]
********************************************* 
changed: [praseodymium.eqiad.wmnet]

TASK: [restart restbase]
****************************************************** 
changed: [praseodymium.eqiad.wmnet]

TASK: [check port 7231]
******************************************************* 
ok: [praseodymium.eqiad.wmnet]

TASK: [wait 10s for LVS]
****************************************************** 
ok: [praseodymium.eqiad.wmnet]

TASK: [check out the deploy repo]
********************************************* 
changed: [xenon.eqiad.wmnet]

TASK: [restart restbase]
****************************************************** 
changed: [xenon.eqiad.wmnet]

TASK: [check port 7231]
******************************************************* 
ok: [xenon.eqiad.wmnet]

TASK: [wait 10s for LVS]
****************************************************** 
ok: [xenon.eqiad.wmnet]

PLAY RECAP
******************************************************************** 
cerium.eqiad.wmnet         : ok=4    changed=2    unreachable=0    failed=0   
praseodymium.eqiad.wmnet   : ok=4    changed=2    unreachable=0    failed=0   
xenon.eqiad.wmnet          : ok=4    changed=2    unreachable=0    failed=0
```

