Lighthouse role
=========
Роль для установки lighthouse

- Скачивание Lighthouse из репозитория
- Конфигурирование Lighthouse

Requirements
------------
- Хост на Ubuntu или Debian
- curl, git
- nginx


Role Variables
--------------
- [./defaults/main.yml](./defaults/main.yml) - предназначен для установки реквизитов подключения
- [./vars/main.yml](./vars/main.yml) - содержит переменные необходимые для установки пакетов и конфигурационных файлов

Dependencies
------------
Необходима роль [clickhouse-role](../clickhouse-role)

В inventory должен быть хост `nginx-host`
```yaml
---
  lighthouse:
    hosts:
      nginx-host:
        ansible_host: IPv4 Address
```
[lighthouse.conf.j2](./templates/lighthouse.conf.j2) > `server_name` - используется при создании конфигурации сервиса


Example Playbook
----------------

```yaml
hosts: lighthouse
roles:
  - role: lighthouse-role
```

License
-------
MIT

Author Information
------------------
- author: Pavel Yakushin
- company: Netology workshop

