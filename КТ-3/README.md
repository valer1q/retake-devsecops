# КТ-3. Система мониторинга Prometheus

## Состав проекта

- `playbook.yml` — установка и настройка Prometheus 2.53.2;
- `templates/prometheus.service.j2` — systemd unit;
- `hosts` — inventory;
- `ansible.cfg` — настройки Ansible;
- `report/` — скриншоты выполнения.

## Запуск

```bash
ansible-playbook -i hosts-local --syntax-check playbook.yml
ansible-playbook -i hosts-local playbook.yml
```

## Проверка

```bash
systemctl status prometheus --no-pager
ufw status
curl -I http://127.0.0.1:9090/-/ready
```

Ожидается состояние `active (running)`, разрешённый TCP-порт 9090 и HTTP-ответ от endpoint готовности Prometheus. В браузере интерфейс доступен по адресу `http://72.56.79.52:9090`.
