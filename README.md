# Edmakas_platform
Edmakas Platform repository


# Выполнено ДЗ №1
 - [ x ] Основное ДЗ
 - [ ] Задание со *

## В процессе сделано:
 - Kластер под управлением minikube
 - Проверка подключения к кластеру 
   ```
   kubectl cluster-info
   ```
 - Запуск дашборда миникуба
   ```
   minikube dashboard
   ```
 - Отказоустойчивость поддерживается таким образом. Поды, управляемые через ReplicaSet восстанавливаются автоматически. kube-apiserver     управляется через сервисы ОС.
 - Создан Dockerfile для образа Nginx веб-серверa
 - Создан манифест для пода, содержащего контейнер с веб-сервером
 - Используется инит-контейнер для создания веб-страницы
 - Веб-страница сохраняется в volume типа emptyDir
 - Для доступа к поду используется kubectl port-forward

## Полезные команды
 - minikube ssh - зайти на воркер
 - docker rm -f $(docker ps -a -q) - удаление всех контейнеров
 - kubectl get pods -n kube-system - смотрим под-ы в заданном namespace-е
 - kubectl delete pod --all -n kube-system - удаляем все под-ы в заданном namespace-е
 - kubectl get cs - состояние controle plane
 - kubectl apply -f web-pod.yaml - запуск манифеста
 - kubectl get pod web -o yaml - смотрим манифест
 - kubectl describe pod web - описание и состояние объекта, включая события
 - kubectl get pods -w - отслеживаем состояние под-ов в онлайне
 - kubectl port-forward --address 0.0.0.0 pod/web 8000:8000 - прокидываем порты

## Как проверить работоспособность:
 - Перейти по ссылке http://localhost:8080

## PR checklist:
 - [X] Выставлен label  homework-1

