# КТ-4. Системы оркестрации

Проект разворачивает Kubernetes-кластер из одной master-ноды и двух worker-нод через kubeadm, containerd и Flannel. После создания кластера разворачивается nginx Deployment.

## Запуск

```bash
ansible-playbook --syntax-check 01-prepare-nodes.yml
ansible-playbook 01-prepare-nodes.yml
ansible-playbook 02-init-control-plane.yml
ansible-playbook 03-join-workers.yml
ansible-playbook 04-nginx-deploy.yml
```

## Проверка

На master:

```bash
kubectl get nodes -o wide
kubectl get pods -A
kubectl get deployment,pods,service
```

Ожидается три узла в состоянии `Ready`, pod'ы Flannel в состоянии `Running`, три nginx-реплики и созданный Service.
