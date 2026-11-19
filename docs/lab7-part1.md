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
