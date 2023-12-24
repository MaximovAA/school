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
changed: [localhost] => (item=instance)
changed: [localhost] => (item=ubuntu)

TASK [Wait for instance(s) deletion to complete] *******************************
ok: [localhost] => (item=instance)
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
ok: [localhost] => (item={'image': 'centos:7', 'name': 'instance'})
ok: [localhost] => (item={'image': 'ubuntu:latest', 'name': 'ubuntu'})

TASK [Create Dockerfiles from image names] *************************************
changed: [localhost] => (item={'image': 'centos:7', 'name': 'instance'})
changed: [localhost] => (item={'image': 'ubuntu:latest', 'name': 'ubuntu'})

TASK [Synchronization the context] *********************************************
changed: [localhost] => (item={'image': 'centos:7', 'name': 'instance'})
ok: [localhost] => (item={'image': 'ubuntu:latest', 'name': 'ubuntu'})

TASK [Discover local Docker images] ********************************************
ok: [localhost] => (item={'diff': [], 'dest': '/root/.cache/molecule/vector-role/default/Dockerfile_centos_7', 'src': '/root/.ansible/tmp/ansible-tmp-1703422889.6175954-12036-206216183120227/source', 'md5sum': '7cd3068447b3fa64265b301e56637814', 'checksum': '86cf5647c3542cd3e8a18787ace2eb98422f513d', 'changed': True, 'uid': 0, 'gid': 0, 'owner': 'root', 'group': 'root', 'mode': '0600', 'state': 'file', 'size': 1037, 'invocation': {'module_args': {'src': '/root/.ansible/tmp/ansible-tmp-1703422889.6175954-12036-206216183120227/source', 'dest': '/root/.cache/molecule/vector-role/default/Dockerfile_centos_7', 'mode': '0600', 'follow': False, '_original_basename': 'Dockerfile.j2', 'checksum': '86cf5647c3542cd3e8a18787ace2eb98422f513d', 'backup': False, 'force': True, 'unsafe_writes': False, 'content': None, 'validate': None, 'directory_mode': None, 'remote_src': None, 'local_follow': None, 'owner': None, 'group': None, 'seuser': None, 'serole': None, 'selevel': None, 'setype': None, 'attributes': None}}, 'failed': False, 'item': {'image': 'centos:7', 'name': 'instance'}, 'ansible_loop_var': 'item', 'i': 0, 'ansible_index_var': 'i'})
ok: [localhost] => (item={'diff': [], 'dest': '/root/.cache/molecule/vector-role/default/Dockerfile_ubuntu_latest', 'src': '/root/.ansible/tmp/ansible-tmp-1703422889.9501915-12036-9737403487627/source', 'md5sum': '4b5371d46746a8dc9fc3cc8bb66381ad', 'checksum': 'c75aaabd95b5bd8d709c54e533f97bb910802695', 'changed': True, 'uid': 0, 'gid': 0, 'owner': 'root', 'group': 'root', 'mode': '0600', 'state': 'file', 'size': 1042, 'invocation': {'module_args': {'src': '/root/.ansible/tmp/ansible-tmp-1703422889.9501915-12036-9737403487627/source', 'dest': '/root/.cache/molecule/vector-role/default/Dockerfile_ubuntu_latest', 'mode': '0600', 'follow': False, '_original_basename': 'Dockerfile.j2', 'checksum': 'c75aaabd95b5bd8d709c54e533f97bb910802695', 'backup': False, 'force': True, 'unsafe_writes': False, 'content': None, 'validate': None, 'directory_mode': None, 'remote_src': None, 'local_follow': None, 'owner': None, 'group': None, 'seuser': None, 'serole': None, 'selevel': None, 'setype': None, 'attributes': None}}, 'failed': False, 'item': {'image': 'ubuntu:latest', 'name': 'ubuntu'}, 'ansible_loop_var': 'item', 'i': 1, 'ansible_index_var': 'i'})

TASK [Build an Ansible compatible image (new)] *********************************
changed: [localhost] => (item=molecule_local/centos:7)
changed: [localhost] => (item=molecule_local/ubuntu:latest)

TASK [Create docker network(s)] ************************************************
skipping: [localhost]

TASK [Determine the CMD directives] ********************************************
ok: [localhost] => (item={'image': 'centos:7', 'name': 'instance'})
ok: [localhost] => (item={'image': 'ubuntu:latest', 'name': 'ubuntu'})

TASK [Create molecule instance(s)] *********************************************
changed: [localhost] => (item=instance)
changed: [localhost] => (item=ubuntu)

TASK [Wait for instance(s) creation to complete] *******************************
FAILED - RETRYING: [localhost]: Wait for instance(s) creation to complete (300 retries left).
changed: [localhost] => (item={'failed': 0, 'started': 1, 'finished': 0, 'ansible_job_id': 'j22699279294.15724', 'results_file': '/root/.ansible_async/j22699279294.15724', 'changed': True, 'item': {'image': 'centos:7', 'name': 'instance'}, 'ansible_loop_var': 'item'})
changed: [localhost] => (item={'failed': 0, 'started': 1, 'finished': 0, 'ansible_job_id': 'j576562098773.15749', 'results_file': '/root/.ansible_async/j576562098773.15749', 'changed': True, 'item': {'image': 'ubuntu:latest', 'name': 'ubuntu'}, 'ansible_loop_var': 'item'})

PLAY RECAP *********************************************************************
localhost                  : ok=9    changed=5    unreachable=0    failed=0    skipped=2    rescued=0    ignored=0

INFO     Running default > prepare
WARNING  Skipping, prepare playbook not configured.
INFO     Running default > converge

PLAY [Converge] ****************************************************************

TASK [Gathering Facts] *********************************************************
ok: [ubuntu]
ok: [instance]

TASK [Include vector-role] *****************************************************

TASK [vector-role : Get vector distrib] ****************************************
fatal: [instance]: FAILED! => {"changed": false, "checksum_dest": null, "checksum_src": "0425ff071083302e50f6004cf9ae6678a0594f37", "dest": "vector-0.34.1.rpm", "elapsed": 8, "msg": "Destination  does not exist", "src": "/root/.ansible/tmp/ansible-tmp-1703423024.955739-16429-231054310782744/tmp0x5Eve", "url": "https://packages.timber.io/vector/0.34.1/vector-0.34.1-1.x86_64.rpm"}
fatal: [ubuntu]: FAILED! => {"changed": false, "checksum_dest": null, "checksum_src": "0425ff071083302e50f6004cf9ae6678a0594f37", "dest": "vector-0.34.1.rpm", "elapsed": 8, "msg": "Destination  does not exist", "src": "/root/.ansible/tmp/ansible-tmp-1703423024.966046-16430-169646525853390/tmp2m_jn_dh", "url": "https://packages.timber.io/vector/0.34.1/vector-0.34.1-1.x86_64.rpm"}

PLAY RECAP *********************************************************************
instance                   : ok=1    changed=0    unreachable=0    failed=1    skipped=0    rescued=0    ignored=0
ubuntu                     : ok=1    changed=0    unreachable=0    failed=1    skipped=0    rescued=0    ignored=0

CRITICAL Ansible return code was 2, command was: ['ansible-playbook', '--inventory', '/root/.cache/molecule/vector-role/default/inventory', '--skip-tags', 'molecule-notest,notest', '/root/ansible/roles/vector-role/molecule/default/converge.yml']
WARNING  An error occurred during the test sequence action: 'converge'. Cleaning up.
INFO     Running default > cleanup
WARNING  Skipping, cleanup playbook not configured.
INFO     Running default > destroy

PLAY [Destroy] *****************************************************************

TASK [Set async_dir for HOME env] **********************************************
ok: [localhost]

TASK [Destroy molecule instance(s)] ********************************************
changed: [localhost] => (item=instance)
changed: [localhost] => (item=ubuntu)

TASK [Wait for instance(s) deletion to complete] *******************************
FAILED - RETRYING: [localhost]: Wait for instance(s) deletion to complete (300 retries left).
changed: [localhost] => (item=instance)
changed: [localhost] => (item=ubuntu)

TASK [Delete docker networks(s)] ***********************************************
skipping: [localhost]

PLAY RECAP *********************************************************************
localhost                  : ok=3    changed=2    unreachable=0    failed=0    skipped=1    rescued=0    ignored=0

INFO     Pruning extra files from scenario ephemeral directory
```
