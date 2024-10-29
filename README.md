# Разворачиваем сайт в Minikube
Набор манифестов для запуска `Django-проекта` в кластере.

### Как поднять кластер Kubernetes в Minikube
Установить [kubectl](https://kubernetes.io/ru/docs/tasks/tools/install-kubectl/) и [minikube](https://minikube.sigs.k8s.io/docs/start/?arch=%2Flinux%2Fx86-64%2Fstable%2Fbinary+download).  

После запустить команду:

```
minikube start --vm-driver=<драйвер>
```
### Как развернуть сайт
Развернуть PostgresQL в кластере с помощью [Helm](https://helm.sh/) и [Helm Chart for PostgreSQL](https://artifacthub.io/packages/helm/bitnami/postgresql).

Скачать репозиторий с кодом и перейти в директорию:

```
cd kubernetes
```
Последовательно выполнить команды:

```
kubectl apply -f secret.yaml
```

```
kubectl apply -f nginx-configmap.yaml
```

```
kubectl apply -f deployment.yaml
```

```
kubectl apply -f service.yaml
```

```
kubectl apply -f ingress.yaml
```

```
kubectl apply -f django-migrate-job.yaml
```

```
kubectl apply -f django-clearsessions.yaml
```

Сайт будет доступен по адресу [star-burger.test](http://star-burger.test)

## Цели проекта

Код написан в учебных целях — это урок в курсе по Python и веб-разработке на сайте [Devman.org](https://dvmn.org).



