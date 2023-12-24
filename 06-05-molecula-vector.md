```bash
INFO     default scenario test matrix: dependency, lint, cleanup, destroy, syntax, create, prepare, converge, idempotence, side_effect, verify, cleanup, destroy
INFO     Performing prerun...
INFO     Set ANSIBLE_LIBRARY=/root/.cache/ansible-compat/f5bcd7/modules:/root/.ansible/plugins/modules:/usr/share/ansible/plugins/modules
INFO     Set ANSIBLE_COLLECTIONS_PATH=/root/.cache/ansible-compat/f5bcd7/collections:/root/.ansible/collections:/usr/share/ansible/collections
INFO     Set ANSIBLE_ROLES_PATH=/root/.cache/ansible-compat/f5bcd7/roles:/root/.ansible/roles:/usr/share/ansible/roles:/etc/ansible/roles
INFO     Running default > dependency
WARNING  Skipping, missing the requirements file.
WARNING  Skipping, missing the requirements file.
INFO     Running default > lint
INFO     Lint is disabled.
INFO     Running default > cleanup
WARNING  Skipping, cleanup playbook not configured.
INFO     Running default > destroy
INFO     Sanity checks: 'docker'

PLAY [Destroy] *****************************************************************

TASK [Set async_dir for HOME env] **********************************************
ok: [localhost]

TASK [Destroy molecule instance(s)] ********************************************
changed: [localhost] => (item=centos)
changed: [localhost] => (item=ubuntu)

TASK [Wait for instance(s) deletion to complete] *******************************
ok: [localhost] => (item=centos)
ok: [localhost] => (item=ubuntu)

TASK [Delete docker networks(s)] ***********************************************
skipping: [localhost]

PLAY RECAP *********************************************************************
localhost                  : ok=3    changed=1    unreachable=0    failed=0    skipped=1    rescued=0    ignored=0

INFO     Running default > syntax

playbook: /root/ansible/roles/vector-role/molecule/default/converge.yml
INFO     Running default > create

PLAY [Create] ******************************************************************

TASK [Set async_dir for HOME env] **********************************************
ok: [localhost]

TASK [Log into a Docker registry] **********************************************
skipping: [localhost] => (item=None)
skipping: [localhost] => (item=None)
skipping: [localhost]

TASK [Check presence of custom Dockerfiles] ************************************
ok: [localhost] => (item={'image': 'centos:7', 'name': 'centos'})
ok: [localhost] => (item={'image': 'ubuntu:latest', 'name': 'ubuntu'})

TASK [Create Dockerfiles from image names] *************************************
changed: [localhost] => (item={'image': 'centos:7', 'name': 'centos'})
changed: [localhost] => (item={'image': 'ubuntu:latest', 'name': 'ubuntu'})

TASK [Synchronization the context] *********************************************
changed: [localhost] => (item={'image': 'centos:7', 'name': 'centos'})
ok: [localhost] => (item={'image': 'ubuntu:latest', 'name': 'ubuntu'})

TASK [Discover local Docker images] ********************************************
ok: [localhost] => (item={'diff': [], 'dest': '/root/.cache/molecule/vector-role/default/Dockerfile_centos_7', 'src': '/root/.ansible/tmp/ansible-tmp-1703445697.2320118-156965-273155919385308/source', 'md5sum': '7cd3068447b3fa64265b301e56637814', 'checksum': '86cf5647c3542cd3e8a18787ace2eb98422f513d', 'changed': True, 'uid': 0, 'gid': 0, 'owner': 'root', 'group': 'root', 'mode': '0600', 'state': 'file', 'size': 1037, 'invocation': {'module_args': {'src': '/root/.ansible/tmp/ansible-tmp-1703445697.2320118-156965-273155919385308/source', 'dest': '/root/.cache/molecule/vector-role/default/Dockerfile_centos_7', 'mode': '0600', 'follow': False, '_original_basename': 'Dockerfile.j2', 'checksum': '86cf5647c3542cd3e8a18787ace2eb98422f513d', 'backup': False, 'force': True, 'unsafe_writes': False, 'content': None, 'validate': None, 'directory_mode': None, 'remote_src': None, 'local_follow': None, 'owner': None, 'group': None, 'seuser': None, 'serole': None, 'selevel': None, 'setype': None, 'attributes': None}}, 'failed': False, 'item': {'image': 'centos:7', 'name': 'centos'}, 'ansible_loop_var': 'item', 'i': 0, 'ansible_index_var': 'i'})
ok: [localhost] => (item={'diff': [], 'dest': '/root/.cache/molecule/vector-role/default/Dockerfile_ubuntu_latest', 'src': '/root/.ansible/tmp/ansible-tmp-1703445697.5380144-156965-203924962516369/source', 'md5sum': '4b5371d46746a8dc9fc3cc8bb66381ad', 'checksum': 'c75aaabd95b5bd8d709c54e533f97bb910802695', 'changed': True, 'uid': 0, 'gid': 0, 'owner': 'root', 'group': 'root', 'mode': '0600', 'state': 'file', 'size': 1042, 'invocation': {'module_args': {'src': '/root/.ansible/tmp/ansible-tmp-1703445697.5380144-156965-203924962516369/source', 'dest': '/root/.cache/molecule/vector-role/default/Dockerfile_ubuntu_latest', 'mode': '0600', 'follow': False, '_original_basename': 'Dockerfile.j2', 'checksum': 'c75aaabd95b5bd8d709c54e533f97bb910802695', 'backup': False, 'force': True, 'unsafe_writes': False, 'content': None, 'validate': None, 'directory_mode': None, 'remote_src': None, 'local_follow': None, 'owner': None, 'group': None, 'seuser': None, 'serole': None, 'selevel': None, 'setype': None, 'attributes': None}}, 'failed': False, 'item': {'image': 'ubuntu:latest', 'name': 'ubuntu'}, 'ansible_loop_var': 'item', 'i': 1, 'ansible_index_var': 'i'})

TASK [Build an Ansible compatible image (new)] *********************************
ok: [localhost] => (item=molecule_local/centos:7)
ok: [localhost] => (item=molecule_local/ubuntu:latest)

TASK [Create docker network(s)] ************************************************
skipping: [localhost]

TASK [Determine the CMD directives] ********************************************
ok: [localhost] => (item={'image': 'centos:7', 'name': 'centos'})
ok: [localhost] => (item={'image': 'ubuntu:latest', 'name': 'ubuntu'})

TASK [Create molecule instance(s)] *********************************************
changed: [localhost] => (item=centos)
changed: [localhost] => (item=ubuntu)

TASK [Wait for instance(s) creation to complete] *******************************
FAILED - RETRYING: [localhost]: Wait for instance(s) creation to complete (300 retries left).
changed: [localhost] => (item={'failed': 0, 'started': 1, 'finished': 0, 'ansible_job_id': 'j36640649997.157240', 'results_file': '/root/.ansible_async/j36640649997.157240', 'changed': True, 'item': {'image': 'centos:7', 'name': 'centos'}, 'ansible_loop_var': 'item'})
changed: [localhost] => (item={'failed': 0, 'started': 1, 'finished': 0, 'ansible_job_id': 'j444988280124.157265', 'results_file': '/root/.ansible_async/j444988280124.157265', 'changed': True, 'item': {'image': 'ubuntu:latest', 'name': 'ubuntu'}, 'ansible_loop_var': 'item'})

PLAY RECAP *********************************************************************
localhost                  : ok=9    changed=4    unreachable=0    failed=0    skipped=2    rescued=0    ignored=0

INFO     Running default > prepare
WARNING  Skipping, prepare playbook not configured.
INFO     Running default > converge

PLAY [Converge] ****************************************************************

TASK [Gathering Facts] *********************************************************
ok: [ubuntu]
ok: [centos]

TASK [Include vector-role] *****************************************************

TASK [vector-role : vector apt install tar] ************************************
skipping: [centos]
included: /root/ansible/roles/vector-role/tasks/pre_install/apt.yml for ubuntu

TASK [vector-role : vector install tar] ****************************************
ok: [ubuntu]

TASK [vector-role : vector yum install tar] ************************************
skipping: [ubuntu]
included: /root/ansible/roles/vector-role/tasks/pre_install/yum.yml for centos

TASK [vector-role : vector install tar] ****************************************
ok: [centos]

TASK [vector-role : Add a group vector] ****************************************
changed: [ubuntu]
changed: [centos]

TASK [vector-role : Add user vector] *******************************************
changed: [ubuntu]
changed: [centos]

TASK [vector-role : vector get distrib] ****************************************
changed: [ubuntu]
changed: [centos]

TASK [vector-role : vector unpack distrib] *************************************
[WARNING]: Relative destination path './' was resolved to absolute path '/'.
changed: [ubuntu]
changed: [centos]

TASK [vector-role : vector install] ********************************************
changed: [ubuntu]
changed: [centos]

TASK [vector-role : vector check installed version] ****************************
ok: [ubuntu]
ok: [centos]

TASK [vector-role : vector create data dir] ************************************
changed: [centos]
changed: [ubuntu]

TASK [vector-role : write using jinja2] ****************************************
changed: [centos]
changed: [ubuntu]

TASK [vector-role : vector | register as service] ******************************
changed: [centos]
changed: [ubuntu]

PLAY RECAP *********************************************************************
centos                     : ok=12   changed=8    unreachable=0    failed=0    skipped=1    rescued=0    ignored=0
ubuntu                     : ok=12   changed=8    unreachable=0    failed=0    skipped=1    rescued=0    ignored=0

INFO     Running default > idempotence

PLAY [Converge] ****************************************************************

TASK [Gathering Facts] *********************************************************
ok: [ubuntu]
ok: [centos]

TASK [Include vector-role] *****************************************************

TASK [vector-role : vector apt install tar] ************************************
skipping: [centos]
included: /root/ansible/roles/vector-role/tasks/pre_install/apt.yml for ubuntu

TASK [vector-role : vector install tar] ****************************************
ok: [ubuntu]

TASK [vector-role : vector yum install tar] ************************************
skipping: [ubuntu]
included: /root/ansible/roles/vector-role/tasks/pre_install/yum.yml for centos

TASK [vector-role : vector install tar] ****************************************
ok: [centos]

TASK [vector-role : Add a group vector] ****************************************
ok: [ubuntu]
ok: [centos]

TASK [vector-role : Add user vector] *******************************************
ok: [ubuntu]
ok: [centos]

TASK [vector-role : vector get distrib] ****************************************
ok: [ubuntu]
ok: [centos]

TASK [vector-role : vector unpack distrib] *************************************
[WARNING]: Relative destination path './' was resolved to absolute path '/'.
ok: [ubuntu]
ok: [centos]

TASK [vector-role : vector install] ********************************************
ok: [ubuntu]
ok: [centos]

TASK [vector-role : vector check installed version] ****************************
ok: [ubuntu]
ok: [centos]

TASK [vector-role : vector create data dir] ************************************
ok: [centos]
ok: [ubuntu]

TASK [vector-role : write using jinja2] ****************************************
ok: [ubuntu]
ok: [centos]

TASK [vector-role : vector | register as service] ******************************
ok: [centos]
ok: [ubuntu]

PLAY RECAP *********************************************************************
centos                     : ok=12   changed=0    unreachable=0    failed=0    skipped=1    rescued=0    ignored=0
ubuntu                     : ok=12   changed=0    unreachable=0    failed=0    skipped=1    rescued=0    ignored=0

INFO     Idempotence completed successfully.
INFO     Running default > side_effect
WARNING  Skipping, side effect playbook not configured.
INFO     Running default > verify
INFO     Running Ansible Verifier

PLAY [Verify] ******************************************************************

TASK [Gather Local Users] ******************************************************
ok: [ubuntu]
ok: [centos]

TASK [Gather Local Groups] *****************************************************
ok: [ubuntu]
ok: [centos]

TASK [Gather Installed Packages] ***********************************************
ok: [ubuntu]
ok: [centos]

PLAY RECAP *********************************************************************
centos                     : ok=3    changed=0    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
ubuntu                     : ok=3    changed=0    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0

INFO     Verifier completed successfully.
INFO     Running default > cleanup
WARNING  Skipping, cleanup playbook not configured.
INFO     Running default > destroy

PLAY [Destroy] *****************************************************************

TASK [Set async_dir for HOME env] **********************************************
ok: [localhost]

TASK [Destroy molecule instance(s)] ********************************************
changed: [localhost] => (item=centos)
changed: [localhost] => (item=ubuntu)

TASK [Wait for instance(s) deletion to complete] *******************************
FAILED - RETRYING: [localhost]: Wait for instance(s) deletion to complete (300 retries left).
changed: [localhost] => (item=centos)
changed: [localhost] => (item=ubuntu)

TASK [Delete docker networks(s)] ***********************************************
skipping: [localhost]

PLAY RECAP *********************************************************************
localhost                  : ok=3    changed=2    unreachable=0    failed=0    skipped=1    rescued=0    ignored=0

INFO     Pruning extra files from scenario ephemeral directory
```
