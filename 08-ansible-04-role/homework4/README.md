Задание 4
-------------------

Прериквизиты:
    OS: Ubuntu

    Код проекта: https://github.com/olegmanzhay/mnt-homeworks/tree/MNT-video/08-ansible-04-role/homework4/playbook

    Roles:  
    src: https://github.com/olegmanzhay/lighthouse-role.git  
    src: https://github.com/olegmanzhay/clickhouse-role.git  
    src: https://github.com/olegmanzhay/vector-role-1.  



# Роль: clickhouse


Установка и настройка ClickHouse — распределённой колоночной СУБД для аналитики больших данных.

## Назначение

Роль автоматизирует:
* загрузку и установку GPG‑ключа репозитория ClickHouse;
* добавление репозитория ClickHouse в систему;
* обновление кэша APT;
* установку пакетов ClickHouse (`clickhouse-common-static`, `clickhouse-client`, `clickhouse-server`);
* запуск и включение сервиса `clickhouse-server`;
* ожидание готовности сервера ClickHouse к приёму запросов.

## Требования

* Ansible ≥ 2.9;
* ОС: Ubuntu/Debian (с поддержкой APT);
* права sudo (`become: yes`) для большинства задач;
* доступ в интернет для загрузки GPG‑ключа и пакетов;
* наличие `curl` и `gpg` в системе.

## Переменные

В роли нет настраиваемых переменных — все параметры жёстко заданы в задачах. При необходимости можно добавить переменные для:

| Переменная | По умолчанию | Описание |
|----------|------------|----------|
| `clickhouse_repo_url` | `https://packages.clickhouse.com/deb` | URL репозитория ClickHouse |
| `clickhouse_version` | `stable` | Версия/ветка ClickHouse для установки |
| `clickhouse_packages` | `["clickhouse-common-static", "clickhouse-client", "clickhouse-server"]` | Список устанавливаемых пакетов |

## Зависимости

Нет внешних зависимостей. Роль самодостаточна.

## Пример использования

```
- hosts: clickhouse_servers
  become: yes
  roles:
    - role: clickhouse
```

## Структура

```
clickhouse/
├── defaults/main.yml
├── handlers/main.yml
├── meta/main.yml
├── tasks/main.yml
├── tests/main.yml
├── vars/main.yml
└── README.md

```


# Роль: lighthouse-nginx

Установка и настройка Nginx с развёртыванием веб‑приложения LightHouse (от VK).

## Назначение

Роль автоматизирует:
* установку веб‑сервера Nginx;
* клонирование репозитория LightHouse из GitHub;
* настройку виртуального хоста Nginx для LightHouse;
* включение сайта LightHouse в Nginx;
* запуск и включение сервиса Nginx;
* проверку доступности веб‑приложения.

## Требования

* Ansible ≥ 2.9;
* ОС: Ubuntu/Debian (с поддержкой APT);
* права sudo (`become: yes`) для большинства задач;
* доступ в интернет для загрузки пакетов и клонирования репозитория;
* установленные `git` и `curl` (или `wget`) на целевом хосте;
* порт 80 открыт и не занят другим сервисом.

## Переменные

В роли нет настраиваемых переменных — все параметры жёстко заданы в задачах. При необходимости можно добавить переменные для:

| Переменная | По умолчанию | Описание |
|----------|------------|----------|
| `lighthouse_repo_url` | `https://github.com/VKCOM/lighthouse` | URL репозитория LightHouse |
| `lighthouse_dest` | `/var/www/lighthouse` | Директория для клонирования репозитория |
| `lighthouse_branch` | `master` | Ветка Git для клонирования |
| `nginx_site_config` | `/etc/nginx/sites-available/lighthouse.conf` | Путь к конфигурационному файлу сайта |

## Зависимости


Нет внешних зависимостей. Роль самодостаточна.

## Пример использования

```
- hosts: web_servers
  become: yes
  roles:
    - role: lighthouse-nginx
```
## Структура

```
lighthouse/
├── defaults/main.yml
├── handlers/main.yml
├── meta/main.yml
├── tasks/main.yml
├── tests/main.yml
├── vars/main.yml
└── README.md

```


# Роль: vector

Установка и настройка Vector — инструмента для сбора, преобразования и отправки логов.

## Назначение

Роль автоматизирует:
* загрузку бинарного архива Vector с официального сайта;
* создание директорий для установки и конфигурации;
* извлечение файлов из архива;
* создание системного пользователя и группы для работы Vector;
* развёртывание конфигурационного файла `vector.toml`;
* валидацию конфигурации Vector;
* настройку и регистрацию systemd‑сервиса;
* запуск и включение сервиса Vector;
* ожидание доступности API Vector для мониторинга.

## Требования

* Ansible ≥ 2.9;
* ОС: Linux (рекомендуется Ubuntu/Debian или CentOS/RHEL);
* права sudo (`become: yes`) для большинства задач;
* доступ в интернет для загрузки архива Vector;
* установленные утилиты `tar` и `gzip` для распаковки архива;
* порт, указанный в `vector_api_port`, должен быть свободен (по умолчанию 8686).

## Переменные

| Переменная | По умолчанию | Описание |
|----------|------------|----------|
| `vector_version` | `0.30.0` | Версия Vector для установки (используется в URL загрузки) |
| `vector_user` | `vector` | Пользователь для запуска сервиса Vector |
| `vector_group` | `vector` | Группа для сервиса Vector |
| `vector_config_path` | `/etc/vector/vector.toml` | Путь к конфигурационному файлу Vector |
| `vector_api_port` | `8686` | Порт для API Vector (используется для проверки здоровья) |

## Зависимости

Нет внешних зависимостей. Роль самодостаточна.

## Пример использования

```
- hosts: logging_servers
  become: yes
  roles:
    - role: vector
```

## Структура

```
vector/
├── defaults/main.yml
├── handlers/main.yml
├── meta/main.yml
├── tasks/main.yml
├── tests/main.yml
├── vars/main.yml
└── README.md

```





