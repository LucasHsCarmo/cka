# Elementos básicos de deploy no kubernetes

- **Pod:** Objeto de menor unidade que representa um grupo de um ou mais containers.

- **ReplicaSet:** Objeto que garante a escalabilidade e resiliência. 

- **Deployment:** Objeto que gerencia o ReplicaSet e controla como as réplicas se comportam quando você as atualiza, fazendo o rollout de uma nova versão de sua aplicação.

## Comandos utilizados

```
kubectl api-resources
```

```
kubectl apply -f primeiropod.yaml
kubectl apply -f primeirors.yaml
kubectl apply -f primeirodeployment.yaml
```

```
kubectl get po
kubectl get rs
kubectl get deploy
```

```
kubectl rollout history deploy
kubectl get rs
kubectl rollout undo deploy primeirodeployment
kubectl set image deploy primeirodeployment meucontainer=kubedevio/nginx-color:green
```

```
kubectl delete all selector app=exemplo
```