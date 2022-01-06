# Elementos básicos de deploy no kubernetes

- **Pod:** Objeto de menor unidade que representa um grupo de um ou mais containers.

- **ReplicaSet:** Objeto que garante a escalabilidade e resiliência. 

- **Deployment:** Objeto que gerencia o ReplicaSet e controla como as réplicas se comportam quando você as atualiza, fazendo o rollout de uma nova versão de sua aplicação.

## Comandos utilizados

* Objetos API de um kind

```
kubectl api-resources
```

* Comandos para criar: Pod, ReplicaSet e Deployment

```
kubectl create -f primeiropod.yaml
kubectl create -f primeirors.yaml
kubectl create -f primeirodeployment.yaml
```

* Comandos para criar ou atualizar: Pod, ReplicaSet e Deployment

```
kubectl apply -f primeiropod.yaml
kubectl apply -f primeirors.yaml
kubectl apply -f primeirodeployment.yaml
```

* Comandos para verificar o que está sendo executado: Pod, ReplicaSet e Deployment

```
kubectl get po
kubectl get rs
kubectl get deploy
```

* Comandos para realizar o rollouts e rollbacks

```
kubectl rollout history deploy
kubectl get rs
kubectl rollout undo deploy primeirodeployment
kubectl set image deploy primeirodeployment meucontainer=kubedevio/nginx-color:green
```

* Testar esse comando aqui

```
kubectl delete all selector app=exemplo
```