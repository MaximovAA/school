```bash
INFO     podman scenario test matrix: dependency, lint, cleanup, destroy, syntax, create, prepare, converge, idempotence, side_effect, verify, cleanup, destroy
INFO     Performing prerun...
INFO     Set ANSIBLE_LIBRARY=/root/.cache/ansible-compat/f5bcd7/modules:/root/.ansible/plugins/modules:/usr/share/ansible/plugins/modules
INFO     Set ANSIBLE_COLLECTIONS_PATH=/root/.cache/ansible-compat/f5bcd7/collections:/root/.ansible/collections:/usr/share/ansible/collections
INFO     Set ANSIBLE_ROLES_PATH=/root/.cache/ansible-compat/f5bcd7/roles:/root/.ansible/roles:/usr/share/ansible/roles:/etc/ansible/roles
INFO     Running podman > dependency
WARNING  Skipping, missing the requirements file.
WARNING  Skipping, missing the requirements file.
INFO     Running podman > lint
INFO     Lint is disabled.
INFO     Running podman > cleanup
WARNING  Skipping, cleanup playbook not configured.
INFO     Running podman > destroy
INFO     Sanity checks: 'podman'

PLAY [Destroy] *****************************************************************

TASK [Get passwd entries for USER env] *****************************************
ok: [localhost]

TASK [Get shell async_dir] *****************************************************
ok: [localhost]

TASK [Set async_dir for HOME env] **********************************************
skipping: [localhost]

TASK [Destroy molecule instance(s)] ********************************************
changed: [localhost] => (item={'image': 'docker.io/pycontribs/centos:8', 'name': 'instance', 'pre_build_image': True})

TASK [Wait for instance(s) deletion to complete] *******************************
changed: [localhost] => (item={'failed': 0, 'started': 1, 'finished': 0, 'ansible_job_id': 'j466942817561.2219', 'results_file': '/root/.ansible_async/j466942817561.2219', 'changed': True, 'item': {'image': 'docker.io/pycontribs/centos:8', 'name': 'instance', 'pre_build_image': True}, 'ansible_loop_var': 'item'})

TASK [Delete podman network dedicated to this scenario] ************************
skipping: [localhost] => (item=instance: None specified)
skipping: [localhost]

PLAY RECAP *********************************************************************
localhost                  : ok=4    changed=2    unreachable=0    failed=0    skipped=2    rescued=0    ignored=0

INFO     Running podman > syntax

playbook: /root/ansible/roles/vector-role/molecule/podman/converge.yml
INFO     Running podman > create

PLAY [Create] ******************************************************************

TASK [Get podman executable path] **********************************************
fatal: [localhost]: FAILED! => {"changed": false, "cmd": "command -v podman", "delta": "0:00:00.003291", "end": "2023-12-24 23:41:45.803549", "msg": "non-zero return code", "rc": 127, "start": "2023-12-24 23:41:45.800258", "stderr": "", "stderr_lines": [], "stdout": "", "stdout_lines": []}

PLAY RECAP *********************************************************************
localhost                  : ok=0    changed=0    unreachable=0    failed=1    skipped=0    rescued=0    ignored=0

CRITICAL Ansible return code was 2, command was: ['ansible-playbook', '--inventory', '/root/.cache/molecule/vector-role/podman/inventory', '--skip-tags', 'molecule-notest,notest', '/usr/local/lib/python3.10/dist-packages/molecule_plugins/podman/playbooks/create.yml']
WARNING  An error occurred during the test sequence action: 'create'. Cleaning up.
INFO     Running podman > cleanup
WARNING  Skipping, cleanup playbook not configured.
INFO     Running podman > destroy

PLAY [Destroy] *****************************************************************

TASK [Get passwd entries for USER env] *****************************************
ok: [localhost]

TASK [Get shell async_dir] *****************************************************
ok: [localhost]

TASK [Set async_dir for HOME env] **********************************************
skipping: [localhost]

TASK [Destroy molecule instance(s)] ********************************************
changed: [localhost] => (item={'image': 'docker.io/pycontribs/centos:8', 'name': 'instance', 'pre_build_image': True})

TASK [Wait for instance(s) deletion to complete] *******************************
changed: [localhost] => (item={'failed': 0, 'started': 1, 'finished': 0, 'ansible_job_id': 'j693171301751.2339', 'results_file': '/root/.ansible_async/j693171301751.2339', 'changed': True, 'item': {'image': 'docker.io/pycontribs/centos:8', 'name': 'instance', 'pre_build_image': True}, 'ansible_loop_var': 'item'})

TASK [Delete podman network dedicated to this scenario] ************************
skipping: [localhost] => (item=instance: None specified)
skipping: [localhost]

PLAY RECAP *********************************************************************
localhost                  : ok=4    changed=2    unreachable=0    failed=0    skipped=2    rescued=0    ignored=0

INFO     Pruning extra files from scenario ephemeral directory
```
