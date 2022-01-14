# Taint

- O taint é usado para marcar que o nó não deve aceitar nenhum pod.

# Comandos utilizados

- Verificar o node2, ponto de atenção para o **Taints** após o describe exibido.

```
kubectl describe node node2
```

- Isso significa que nenhum pod poderá agendar no node2 após um novo scale e os pods que estavam alocados no node2 permaneceram nesse ambiente

```
kubectl taint node node2 key1=value1:NoSchedule
kubectl describe node node2
kubectl get po -o wide
kubectl edit deploy deployment-nginx
watch kubectl get po -o wide
```

- Remover o taint, basta add o sinal de **-** no final do comando 

```
* kubectl taint node node2 key1=value1:NoSchedule-
kubectl describe node node2
kubectl get po -o wide
kubectl edit deploy deployment-nginx
watch kubectl get po -o wide
```

- Isso significa que nenhum pod poderá agendar no node3 e todos os pods que estavam nesse ambiente serão rebalanciados para os outros nodes

```
kubectl taint node node3 key1=value1:NoExecute
kubectl describe node node3
kubectl get po -o wide
kubectl edit deploy deployment-nginx
watch kubectl get po -o wide
```

- Remover o taint, basta add o sinal de **-** no final do comando

```
* kubectl taint node node3 key1=value1:NoExecute-
kubectl describe node node3
kubectl get po -o wide
kubectl edit deploy deployment-nginx
watch kubectl get po -o wide
```

- Nesse caso é interessante fazer o scale dos pods depois de executar o comando **kubectl taint node node3 key1=value1:NoExecute-**

```
kubectl scale --replicas=1 deploy deployment-nginx
kubectl scale --replicas=6 deploy deployment-nginx
```