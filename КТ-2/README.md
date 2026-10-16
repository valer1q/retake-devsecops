# КТ-2. ONLYOFFICE Workspace через Ansible

## Подготовка

Ansible и SSH-ключ как в КТ-1. ВМ: 4 ядра, 8 ГБ ОЗУ, 40 ГБ диска.
В `hosts` указать IP ВМ, в `group_vars/DOCKER` пароль sudo. Запуск: `ansible-playbook <файл>`.

## Файлы

| Файл | Что делает |
|---|---|
| `ansible.cfg` | настройки Ansible |
| `hosts` | сервер для установки |
| `group_vars/DOCKER` | пароль sudo |
| `01-docker.yml` | установка Docker и тестовые контейнеры |
| `02-onlyoffice.yml` | установка ONLYOFFICE Workspace скриптом в Docker, без почтового сервера |
