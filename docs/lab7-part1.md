# Отчёт: Лабораторная работа 7 (часть 1) — ToDo backend в minikube

## Задание 1. Запуск minikube и знакомство с кластером

- **Сколько узлов в вашем кластере?** В кластере 1 узел (`minikube`).
- **2–3 компонента control plane в kube-system:** `kube-apiserver-minikube`, `etcd-minikube`, `kube-scheduler-minikube` и `kube-controller-manager-minikube`.
- <img width="822" height="412" alt="image" src="https://github.com/user-attachments/assets/a1be48bc-38db-42b9-983b-4aaaaf312197" />


## Задание 2. Pod без Deployment

- **Появился ли Pod снова после удаления? Почему?** Нет, Pod не появился снова, так как он был создан напрямую без контроллера (`Deployment` / `ReplicaSet`), который восстанавливает удалённые экземпляры.
- <img width="786" height="424" alt="image" src="https://github.com/user-attachments/assets/2a52da1f-fc1d-4cc1-93d0-42d3310668af" />


## Задание 3. Backend в Kubernetes: Deployment + Service
<img width="1039" height="615" alt="image" src="https://github.com/user-attachments/assets/73683a37-9e54-4974-9eeb-0ed6776ec63a" />


## Задание 4. Самовосстановление

- **Совпадает ли имя нового Pod со старым?** Нет, новый Pod получил другое имя (`todo-backend-5868775c7-2wfdx` вместо `todo-backend-5868775c7-dznn6`) и новый IP-адрес.
- **Кто создал новый Pod и почему? В чём отличие от задания 2?** Новый Pod создал контроллер `ReplicaSet` (управляемый `Deployment`), чтобы поддержать заданное число реплик (`replicas: 2`); в задании 2 контроллера не было, поэтому удалённый Pod не воссоздавался.
- <img width="766" height="131" alt="image" src="https://github.com/user-attachments/assets/283172cc-09a6-40e3-80f2-2099f03d81f9" />





