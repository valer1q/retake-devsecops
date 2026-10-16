# КТ-1. Ansible playbook'и

## Подготовка

```bash
sudo apt-add-repository ppa:ansible/ansible
sudo apt update
sudo apt install ansible sshpass -y
ssh-keygen -t rsa
ssh-copy-id sysadmin@IP-сервера
```

В `hosts` указать IP серверов, в `group_vars/DEVELOP` пароль sudo. Запуск: `ansible-playbook <файл>`.

## Файлы

| Файл | Что делает |
|---|---|
| `ansible.cfg` | настройки Ansible |
| `hosts` | список серверов и групп |
| `group_vars/DEVELOP` | пароль sudo |
| `files/` | страница сайта, конфиги nginx и Prometheus |
| `01-nginx.yml` | установка и настройка Nginx |
| `02-user.yml` | пользователь newadmin с правами sudo |
| `03-update.yml` | обновление пакетов и перезагрузка |
| `04-backup.yml` | резервные копии конфигов |
| `05-services.yml` | остановка, запуск и перезапуск nginx |
| `06-firewall.yml` | настройка файрвола UFW |
| `07-postgresql.yml` | PostgreSQL, пользователь и база данных |
| `08-git-deploy.yml` | деплой сайта из Git |
| `09-lineinfile.yml` | замена строк в index.html |
| `09-sysctl.yml` | параметры ядра через sysctl |
| `10-prometheus.yml` | Prometheus и Node Exporter |
