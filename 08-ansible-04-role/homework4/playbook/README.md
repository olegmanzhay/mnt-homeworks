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