# КТ-4. Кластер Kubernetes и сервис nginx

## Подготовка

Ansible и SSH-ключ как в КТ-1. 3 ВМ с Ubuntu 22.04 / 24.04, на мастере минимум 2 ядра и 2 ГБ ОЗУ.
В `hosts` указать IP нод, в `group_vars/K8S` пароль sudo. Плейбуки запускать по порядку: `ansible-playbook <файл>`.

## Файлы

| Файл | Что делает |
|---|---|
| `ansible.cfg` | настройки Ansible |
| `hosts` | мастер и рабочие ноды |
| `group_vars/K8S` | пароль sudo |
| `files/nginx-rc.yml` | Replication Controller nginx на 6 реплик |
| `files/nginx-services.yml` | сервисы nginx-http и nginx-https |
| `01-prepare-nodes.yml` | Docker, bridge-utils и подготовка нод |
| `02-install-kubernetes.yml` | установка kubelet, kubeadm, kubectl |
| `03-cluster-init.yml` | создание кластера, сеть flannel, подключение нод |
| `04-nginx.yml` | запуск nginx и сервисов в кластере |
| `Отчет_КТ-4.docx` | отчёт о работе |
