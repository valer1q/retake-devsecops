# КТ-1: Написание простых Ansible Playbook

## Подготовка

Выполнить на управляющей Ubuntu-машине:

```bash
sudo apt update
sudo apt install ansible sshpass python3-passlib -y
ansible-galaxy collection install community.general ansible.posix
ansible --version
```

Проверить адрес и пользователя в `hosts`, затем перейти в каталог КТ-1 и проверить соединение. Для входа по паролю используйте `-k`, пароль вводится в интерактивном режиме и не записывается в файлы:

```bash
ansible all -m ping -k
```

## Запуск

```bash
ansible-playbook 01-nginx.yml
ansible-playbook 02-username.yml
ansible-playbook 03-system-update.yml
ansible-playbook 04-backup.yml
ansible-playbook 05-service.yml
ansible-playbook 06-firewall.yml
ansible-playbook 07-postgresql.yml
ansible-playbook 08-git-deploy.yml
ansible-playbook 09-lineinfile.yml
ansible-playbook 10-sysctl.yml
ansible-playbook 11-prometheus.yml
```

Сценарий `08-git-deploy.yml` использует репозиторий `https://github.com/valer1q/prilojeniye.git`.

## Проверка результата

```bash
systemctl status nginx postgresql prometheus
id newadmin
sudo ufw status verbose
ls -l /var/backups/configuration.tar.gz
cat /var/www/html/index.html
sysctl net.ipv4.ip_forward
```

Для отчёта сделать скриншоты терминала с командой запуска, именем Playbook и успешным `PLAY RECAP`, а также отдельные скриншоты команд проверки.

## Проверка синтаксиса

```bash
for file in *.yml; do ansible-playbook --syntax-check "$file"; done
```
