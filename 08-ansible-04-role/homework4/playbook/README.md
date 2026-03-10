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
basepython = python3.8
envlist = py{38}-ansible-{2.10,2.12}
skipsdist = true

[testenv]
passenv = *
deps =
    -r tox-requirements.txt
    2.10: ansible == 2.10.*
    2.13: ansible == 2.13.*
commands =
{posargs:molecule test -s light --destroy always}
```

```
admin-oleg@admin-oleg-VMware-Virtual-Platform:~/Desktop/Netology/mnt-homeworks/08-ansible-04-role/homework4/playbook/roles/vector$ docker run --privileged=True -v /home/admin-oleg/Desktop/Netology/mnt-homeworks/08-ansible-04-role/homework4/playbook/roles/vector:/opt/vector-role -w /opt/vector-role -it aragast/netology:latest /bin/bash
[root@575e4ad9cd4f vector-role]# tox
py38-ansible-2.10 installed: ansible==2.10.7,ansible-base==2.10.17,ansible-compat==3.0.2,ansible-core==2.13.13,arrow==1.4.0,attrs==25.3.0,backports.zoneinfo==0.2.1,binaryornot==0.4.4,certifi==2026.2.25,cffi==1.17.1,chardet==5.2.0,charset-normalizer==3.4.5,click==8.1.8,click-help-colors==0.9.4,cookiecutter==2.6.0,cryptography==46.0.5,distro==1.9.0,enrich==1.2.7,idna==3.11,importlib_resources==6.4.5,Jinja2==3.1.6,jmespath==1.0.1,jsonschema==4.23.0,jsonschema-specifications==2023.12.1,lxml==6.0.2,markdown-it-py==3.0.0,MarkupSafe==2.1.5,mdurl==0.1.2,molecule==4.0.4,molecule-podman==2.0.3,packaging==26.0,pkgutil_resolve_name==1.3.10,pluggy==1.5.0,pycparser==2.23,Pygments==2.19.2,python-dateutil==2.9.0.post0,python-slugify==8.0.4,PyYAML==6.0.3,referencing==0.35.1,requests==2.32.4,resolvelib==0.8.1,rich==14.3.3,rpds-py==0.20.1,selinux==0.2.1,six==1.17.0,subprocess-tee==0.4.2,text-unidecode==1.3,typing_extensions==4.13.2,urllib3==2.2.3,zipp==3.20.2
py38-ansible-2.10 run-test-pre: PYTHONHASHSEED='3393353090'
py38-ansible-2.12 installed: ansible-compat==3.0.2,ansible-core==2.13.13,arrow==1.4.0,attrs==25.3.0,backports.zoneinfo==0.2.1,binaryornot==0.4.4,certifi==2026.2.25,cffi==1.17.1,chardet==5.2.0,charset-normalizer==3.4.5,click==8.1.8,click-help-colors==0.9.4,cookiecutter==2.6.0,cryptography==46.0.5,distro==1.9.0,enrich==1.2.7,idna==3.11,importlib_resources==6.4.5,Jinja2==3.1.6,jmespath==1.0.1,jsonschema==4.23.0,jsonschema-specifications==2023.12.1,lxml==6.0.2,markdown-it-py==3.0.0,MarkupSafe==2.1.5,mdurl==0.1.2,molecule==4.0.4,molecule-podman==2.0.3,packaging==26.0,pkgutil_resolve_name==1.3.10,pluggy==1.5.0,pycparser==2.23,Pygments==2.19.2,python-dateutil==2.9.0.post0,python-slugify==8.0.4,PyYAML==6.0.3,referencing==0.35.1,requests==2.32.4,resolvelib==0.8.1,rich==14.3.3,rpds-py==0.20.1,selinux==0.2.1,six==1.17.0,subprocess-tee==0.4.2,text-unidecode==1.3,typing_extensions==4.13.2,urllib3==2.2.3,zipp==3.20.2
py38-ansible-2.12 run-test-pre: PYTHONHASHSEED='3393353090'
______________________________________________________________________________________________ summary _______________________________________________________________________________________________
  py38-ansible-2.10: commands succeeded
  py38-ansible-2.12: commands succeeded
  congratulations :)
```