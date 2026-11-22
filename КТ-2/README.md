# КТ-2. Установка Docker и создание контейнеров через Ansible

## Состав

- `hosts` — inventory с целевым сервером.
- `ansible.cfg` — настройки Ansible.
- `playbook.yml` — установка Docker, Python-модуля Docker, загрузка образа Ubuntu и создание контейнеров.

## Установка зависимостей

На управляющей машине:

```bash
sudo apt update
sudo apt install ansible-core sshpass python3-passlib -y
ansible-galaxy collection install community.docker
```

## Проверка и запуск

```bash
ansible all -m ping
ansible-playbook playbook.yml
```

Проверка синтаксиса:

```bash
ansible-playbook --syntax-check playbook.yml
```

Ожидаемый результат запуска — `failed=0` и четыре изменённых контейнера.

## Проверка на сервере

```bash
docker ps -a
```

Должны присутствовать контейнеры `docker1`, `docker2`, `docker3`, `docker4` на основе образа `ubuntu` с командой `sleep 1d`.

Дополнительные проверки:

```bash
docker image ls ubuntu
docker inspect docker1 --format '{{.Config.Cmd}}'
systemctl is-active docker
```

Для отчёта нужны скриншоты проверки синтаксиса, успешного `PLAY RECAP` и вывода `docker ps -a`.
