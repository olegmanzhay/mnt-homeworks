## Molecule

Проработал запуск тестов на ubuntu:22.04 и debian:11  
Ссылка на коммит: https://github.com/olegmanzhay/mnt-homeworks/commit/249c2727caf3960fbb1f6f7af8fb7e3dbbd45034



```
TASK [Add container to molecule_inventory] *************************************
ok: [localhost] => (item=molecule-ubuntu)
ok: [localhost] => (item=molecule-debian11)

TASK [Dump molecule_inventory] *************************************************
[WARNING]: Skipping unexpected key (molecule) in group (all), only "vars", "children" and "hosts" are valid
changed: [localhost]

TASK [Force inventory refresh] *************************************************

TASK [Fail if molecule group is missing] ***************************************
ok: [localhost] => {
    "changed": false,
    "msg": "All assertions passed"
}

PLAY [Validate that inventory was refreshed] ***********************************

TASK [Check uname] *************************************************************
ok: [molecule-debian11]
ok: [molecule-ubuntu]

TASK [Display uname info] ******************************************************
ok: [molecule-debian11] => {
    "msg": "Linux 3bccbbeddb27 6.17.0-14-generic #14~24.04.1-Ubuntu SMP PREEMPT_DYNAMIC Thu Jan 15 15:52:10 UTC 2 x86_64 GNU/Linux\n"
}
ok: [molecule-ubuntu] => {
    "msg": "Linux 2df69bbce21f 6.17.0-14-generic #14~24.04.1-Ubuntu SMP PREEMPT_DYNAMIC Thu Jan 15 15:52:10 UTC 2 x86_64 x86_64 x86_64 GNU/Linux\n"
}

PLAY RECAP *********************************************************************
localhost                  : ok=5    changed=2    unreachable=0    failed=0    skipped=1    rescued=0    ignored=0
molecule-debian11          : ok=2    changed=0    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
molecule-ubuntu            : ok=2    changed=0    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0

INFO     default ➜ create: Executed: Successful
INFO     default ➜ prepare: Executing
[WARNING]: Skipping unexpected key (molecule) in group (all), only "vars", "children" and "hosts" are valid

PLAY [Prepare container — install Python] **************************************

TASK [Install Python 3] ********************************************************
ok: [molecule-ubuntu]
ok: [molecule-debian11]

PLAY RECAP *********************************************************************
molecule-debian11          : ok=1    changed=0    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
molecule-ubuntu            : ok=1    changed=0    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0

INFO     default ➜ prepare: Executed: Successful
INFO     default ➜ converge: Executing
[WARNING]: Skipping unexpected key (molecule) in group (all), only "vars", "children" and "hosts" are valid

PLAY [Fail if molecule group is missing] ***************************************

TASK [Gathering Facts] *********************************************************
ok: [localhost]

TASK [Print some info] *********************************************************
ok: [localhost] => {
    "msg": {
        "all": [
            "molecule-debian11",
            "molecule-ubuntu"
        ],
        "molecule": [
            "molecule-debian11",
            "molecule-ubuntu"
        ],
        "ungrouped": []
    }
}

TASK [Assert group existence] **************************************************
ok: [localhost] => {
    "changed": false,
    "msg": "All assertions passed"
}

PLAY [Converge] ****************************************************************

TASK [Check uname] *************************************************************
ok: [molecule-debian11]
ok: [molecule-ubuntu]

TASK [Print some info] *********************************************************
ok: [molecule-debian11] => {
    "changed": false,
    "msg": "All assertions passed"
}
ok: [molecule-ubuntu] => {
    "changed": false,
    "msg": "All assertions passed"
}

TASK [Apply vector role] *******************************************************
included: vector for molecule-debian11, molecule-ubuntu

TASK [vector : Download Vector to remote host] *********************************
changed: [molecule-debian11]
changed: [molecule-ubuntu]

TASK [vector : Create destination directory for Vector] ************************
changed: [molecule-ubuntu]
changed: [molecule-debian11]

TASK [vector : Extract Vector archive] *****************************************
changed: [molecule-debian11]
changed: [molecule-ubuntu]

TASK [vector : Create vector group] ********************************************
changed: [molecule-debian11]
changed: [molecule-ubuntu]

TASK [vector : Create vector user] *********************************************
changed: [molecule-debian11]
changed: [molecule-ubuntu]

TASK [vector : Ensure Vector config directory exists] **************************
changed: [molecule-ubuntu]
changed: [molecule-debian11]

TASK [vector : Ensure Vector data directory exists] ****************************
changed: [molecule-debian11]
changed: [molecule-ubuntu]

TASK [vector : Deploy Vector configuration] ************************************
changed: [molecule-debian11]
changed: [molecule-ubuntu]

TASK [vector : Validate Vector configuration] **********************************
ok: [molecule-debian11]
ok: [molecule-ubuntu]

TASK [vector : Start Vector in background with shell (logs to /tmp/logs_vector.txt)] ***
ok: [molecule-ubuntu]
ok: [molecule-debian11]

PLAY RECAP *********************************************************************
localhost                  : ok=3    changed=0    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
molecule-debian11          : ok=13   changed=8    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
molecule-ubuntu            : ok=13   changed=8    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0

INFO     default ➜ converge: Executed: Successful
INFO     default ➜ idempotence: Executing
[WARNING]: Skipping unexpected key (molecule) in group (all), only "vars", "children" and "hosts" are valid

PLAY [Fail if molecule group is missing] ***************************************

TASK [Gathering Facts] *********************************************************
ok: [localhost]

TASK [Print some info] *********************************************************
ok: [localhost] => {
    "msg": {
        "all": [
            "molecule-debian11",
            "molecule-ubuntu"
        ],
        "molecule": [
            "molecule-debian11",
            "molecule-ubuntu"
        ],
        "ungrouped": []
    }
}

TASK [Assert group existence] **************************************************
ok: [localhost] => {
    "changed": false,
    "msg": "All assertions passed"
}

PLAY [Converge] ****************************************************************

TASK [Check uname] *************************************************************
ok: [molecule-debian11]
ok: [molecule-ubuntu]

TASK [Print some info] *********************************************************
ok: [molecule-debian11] => {
    "changed": false,
    "msg": "All assertions passed"
}
ok: [molecule-ubuntu] => {
    "changed": false,
    "msg": "All assertions passed"
}

TASK [Apply vector role] *******************************************************
included: vector for molecule-debian11, molecule-ubuntu

TASK [vector : Download Vector to remote host] *********************************
ok: [molecule-debian11]
ok: [molecule-ubuntu]

TASK [vector : Create destination directory for Vector] ************************
ok: [molecule-debian11]
ok: [molecule-ubuntu]

TASK [vector : Extract Vector archive] *****************************************
ok: [molecule-debian11]
ok: [molecule-ubuntu]

TASK [vector : Create vector group] ********************************************
ok: [molecule-debian11]
ok: [molecule-ubuntu]

TASK [vector : Create vector user] *********************************************
ok: [molecule-debian11]
ok: [molecule-ubuntu]

TASK [vector : Ensure Vector config directory exists] **************************
ok: [molecule-ubuntu]
ok: [molecule-debian11]

TASK [vector : Ensure Vector data directory exists] ****************************
ok: [molecule-debian11]
ok: [molecule-ubuntu]

TASK [vector : Deploy Vector configuration] ************************************
ok: [molecule-debian11]
ok: [molecule-ubuntu]

TASK [vector : Validate Vector configuration] **********************************
ok: [molecule-debian11]
ok: [molecule-ubuntu]

TASK [vector : Start Vector in background with shell (logs to /tmp/logs_vector.txt)] ***
ok: [molecule-debian11]
ok: [molecule-ubuntu]

PLAY RECAP *********************************************************************
localhost                  : ok=3    changed=0    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
molecule-debian11          : ok=13   changed=0    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
molecule-ubuntu            : ok=13   changed=0    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0

INFO     default ➜ idempotence: Executed: Successful
INFO     default ➜ side_effect: Executing
WARNING  default ➜ side_effect: Executed: Missing playbook (Remove from test_sequence to suppress)
INFO     default ➜ verify: Executing
[WARNING]: Skipping unexpected key (molecule) in group (all), only "vars", "children" and "hosts" are valid

PLAY [Verify Vector role functionality] ****************************************

TASK [Gathering Facts] *********************************************************
ok: [molecule-debian11]
ok: [molecule-ubuntu]

TASK [Check Vector configuration validity] *************************************
ok: [molecule-debian11]
ok: [molecule-ubuntu]

TASK [Assert Vector configuration is valid] ************************************
ok: [molecule-debian11] => {
    "changed": false,
    "msg": "Vector configuration is valid"
}
ok: [molecule-ubuntu] => {
    "changed": false,
    "msg": "Vector configuration is valid"
}

TASK [Check if Vector process is running (via pidof)] **************************
ok: [molecule-debian11]
ok: [molecule-ubuntu]

TASK [Assert Vector process is running] ****************************************
ok: [molecule-debian11] => {
    "changed": false,
    "msg": "Vector process is running with PID 5069"
}
ok: [molecule-ubuntu] => {
    "changed": false,
    "msg": "Vector process is running with PID 903"
}

TASK [Check log file existence] ************************************************
ok: [molecule-ubuntu]
ok: [molecule-debian11]

TASK [Assert log file exists and is not empty] *********************************
ok: [molecule-debian11] => {
    "changed": false,
    "msg": "Log file /tmp/logs_vector.txt exists and contains data"
}
ok: [molecule-ubuntu] => {
    "changed": false,
    "msg": "Log file /tmp/logs_vector.txt exists and contains data"
}

PLAY RECAP *********************************************************************
molecule-debian11          : ok=7    changed=0    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
molecule-ubuntu            : ok=7    changed=0    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0

INFO     default ➜ verify: Executed: Successful
```

## OracleLinux 

Тест сценарий упал, так как нет apt-get
```
TASK [Install Python 3] ********************************************************
[ERROR]: Task failed: Action failed: non-zero return code
Origin: /home/admin-oleg/Desktop/Netology/mnt-homeworks/08-ansible-04-role/homework4/playbook/roles/vector/molecule/default/prepare.yml:6:7

4   gather_facts: false
5   tasks:
6     - name: Install Python 3
        ^ column 7

fatal: [oraclelinux]: FAILED! => {"changed": false, "msg": "non-zero return code", "rc": 127, "stderr": "/bin/sh: apt-get: command not found\n", "stderr_lines": ["/bin/sh: apt-get: command not found"], "stdout": "", "stdout_lines": []}
```

# TOX

```
docker run --privileged=True -v /home/admin-oleg/Desktop/Netology/mnt-homeworks/08-ansible-04-role/homework4/playbook/roles/vector:/opt/vector-role -w /opt/vector-role -it aragast/netology:latest /bin/bash
```

```
[root@c88527267680 vector-role]# tox
py37-ansible210 create: /opt/vector-role/.tox/py37-ansible210
py37-ansible210 installdeps: -rtox-requirements.txt, ansible<3.0
```

При выполнении команды tox - получаю следующие ошибки 

Использовался такой tox.ini
```
[tox]
minversion = 1.8
basepython = python3.6
envlist = py36-molecule-light
skipsdist = true

[testenv]
passenv = *
deps =
    -r tox-requirements.txt
    ansible210: ansible<3.0
    ansible30: ansible<3.1
commands =
    molecule test -s light --destroy always
```

```
(venv) admin-oleg@admin-oleg-VMware-Virtual-Platform:~/Desktop/Netology/mnt-homeworks/08-ansible-04-role/homework4/playbook/roles/vector$ docker run --privileged=True -v /home/admin-oleg/Desktop/Netology/mnt-homeworks/08-ansible-04-role/homework4/playbook/roles/vector:/opt/vector-role -w /opt/vector-role -it aragast/netology:latest /bin/bash
[root@65aa52e6de90 vector-role]# tox
py36-molecule-light recreate: /opt/vector-role/.tox/py36-molecule-light
py36-molecule-light installdeps: -rtox-requirements.txt
py36-molecule-light installed: ansible-compat==1.0.0,arrow==1.2.3,bcrypt==4.0.1,binaryornot==0.4.4,cached-property==1.5.2,Cerberus==1.3.5,certifi==2025.4.26,cffi==1.15.1,chardet==5.0.0,charset-normalizer==2.0.12,click==8.0.4,click-help-colors==0.9.4,commonmark==0.9.1,cookiecutter==1.7.3,cryptography==40.0.2,dataclasses==0.8,distro==1.9.0,enrich==1.2.7,idna==3.10,importlib-metadata==4.8.3,Jinja2==3.0.3,jinja2-time==0.2.0,jmespath==0.10.0,lxml==5.4.0,MarkupSafe==2.0.1,molecule==3.6.1,molecule-podman==1.1.0,packaging==21.3,paramiko==2.12.0,pluggy==1.0.0,poyo==0.5.0,pycparser==2.21,Pygments==2.14.0,PyNaCl==1.5.0,pyparsing==3.1.4,python-dateutil==2.9.0.post0,python-slugify==6.1.2,PyYAML==6.0.1,requests==2.27.1,rich==12.6.0,selinux==0.2.1,six==1.17.0,subprocess-tee==0.3.5,text-unidecode==1.3,typing_extensions==4.1.1,urllib3==1.26.20,zipp==3.6.0
py36-molecule-light run-test-pre: PYTHONHASHSEED='3497928613'
py36-molecule-light run-test: commands[0] | molecule test -s light --destroy always
Traceback (most recent call last):
  File "/opt/vector-role/.tox/py36-molecule-light/bin/molecule", line 5, in <module>
    from molecule.__main__ import main
  File "/opt/vector-role/.tox/py36-molecule-light/lib/python3.6/site-packages/molecule/__main__.py", line 24, in <module>
    from molecule.shell import main
  File "/opt/vector-role/.tox/py36-molecule-light/lib/python3.6/site-packages/molecule/shell.py", line 29, in <module>
    from molecule import command, logger
  File "/opt/vector-role/.tox/py36-molecule-light/lib/python3.6/site-packages/molecule/command/__init__.py", line 27, in <module>
    from molecule.command import base  # noqa
  File "/opt/vector-role/.tox/py36-molecule-light/lib/python3.6/site-packages/molecule/command/base.py", line 33, in <module>
    import molecule.scenarios
  File "/opt/vector-role/.tox/py36-molecule-light/lib/python3.6/site-packages/molecule/scenarios.py", line 24, in <module>
    from molecule import util
  File "/opt/vector-role/.tox/py36-molecule-light/lib/python3.6/site-packages/molecule/util.py", line 40, in <module>
    from molecule.app import app
  File "/opt/vector-role/.tox/py36-molecule-light/lib/python3.6/site-packages/molecule/app.py", line 13, in <module>
    app = App()
  File "/opt/vector-role/.tox/py36-molecule-light/lib/python3.6/site-packages/molecule/app.py", line 10, in __init__
    self.runtime = Runtime(isolated=True)
  File "/opt/vector-role/.tox/py36-molecule-light/lib/python3.6/site-packages/ansible_compat/runtime.py", line 84, in __init__
    self.config = AnsibleConfig()
  File "/opt/vector-role/.tox/py36-molecule-light/lib/python3.6/site-packages/ansible_compat/config.py", line 432, in __init__
    ["ansible-config", "dump"], universal_newlines=True, env=env
  File "/usr/lib64/python3.6/subprocess.py", line 356, in check_output
    **kwargs).stdout
  File "/usr/lib64/python3.6/subprocess.py", line 423, in run
    with Popen(*popenargs, **kwargs) as process:
  File "/usr/lib64/python3.6/subprocess.py", line 729, in __init__
    restore_signals, start_new_session)
  File "/usr/lib64/python3.6/subprocess.py", line 1364, in _execute_child
    raise child_exception_type(errno_num, err_msg, err_filename)
FileNotFoundError: [Errno 2] No such file or directory: 'ansible-config': 'ansible-config'
ERROR: InvocationError for command /opt/vector-role/.tox/py36-molecule-light/bin/molecule test -s light --destroy always (exited with code 1)
_____________________________________________________________________________________ summary ______________________________________________________________________________________
ERROR:   py36-molecule-light: commands failed
[root@65aa52e6de90 vector-role]# which ansible
/usr/bin/which: no ansible in (/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin)
[root@65aa52e6de90 vector-role]# which ansible-config
/usr/bin/which: no ansible-config in (/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin)
[root@65aa52e6de90 vector-role]# ansible --version
bash: ansible: command not found
[root@65aa52e6de90 vector-role]# ansible
bash: ansible: command not found
[root@65aa52e6de90 vector-role]# 
```