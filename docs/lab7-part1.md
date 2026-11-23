# Отчёт: Лабораторная работа 7 (часть 1) — ToDo backend в minikube

## Задание 1. Запуск minikube и знакомство с кластером

- **Сколько узлов в вашем кластере?** В кластере 1 узел (`minikube`).
- **2–3 компонента control plane в kube-system:** `kube-apiserver-minikube`, `etcd-minikube`, `kube-scheduler-minikube` и `kube-controller-manager-minikube`.

## Задание 2. Pod без Deployment

- **Появился ли Pod снова после удаления? Почему?** Нет, Pod не появился снова, так как он был создан напрямую без контроллера (`Deployment` / `ReplicaSet`), который восстанавливает удалённые экземпляры.

## Задание 3. Backend в Kubernetes: Deployment + Service

## Задание 4. Самовосстановление

- **Совпадает ли имя нового Pod со старым?** Нет, новый Pod получил другое имя (`todo-backend-5868775c7-2wfdx` вместо `todo-backend-5868775c7-dznn6`) и новый IP-адрес.
- **Кто создал новый Pod и почему? В чём отличие от задания 2?** Новый Pod создал контроллер `ReplicaSet` (управляемый `Deployment`), чтобы поддержать заданное число реплик (`replicas: 2`); в задании 2 контроллера не было, поэтому удалённый Pod не воссоздавался.
<img width="1099" height="606" alt="image" src="https://github.com/user-attachments/assets/0ecc5d44-61c9-4007-9e61-c0dda19a99a2" />
<img width="801" height="653" alt="image" src="https://github.com/user-attachments/assets/c105be1e-133c-40a8-bdcd-08ac35a4df2c" />
<img width="1222" height="570" alt="image" src="https://github.com/user-attachments/assets/0171a1ff-674d-4a4a-b11a-5e5a38591f3d" />
<img width="1093" height="334" alt="image" src="https://github.com/user-attachments/assets/53a4c16c-6a17-4b79-a048-d25a13310bf5" />
<img width="756" height="253" alt="image" src="https://github.com/user-attachments/assets/ad92f1a1-9923-4f0a-8950-c707c5f18ed7" />




