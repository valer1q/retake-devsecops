# КТ-3. Установка Prometheus

## Подготовка

Ansible и SSH-ключ как в КТ-1.
В `hosts` указать IP сервера, в `group_vars/PROMETHEUS` пароль sudo. Запуск: `ansible-playbook 01-prometheus.yml`.

## Файлы

| Файл | Что делает |
|---|---|
| `ansible.cfg` | настройки Ansible |
| `hosts` | сервер для установки |
| `group_vars/PROMETHEUS` | пароль sudo |
| `files/prometheus.service` | служба systemd для Prometheus |
| `01-prometheus.yml` | установка Prometheus из архива по шагам задания |
