# Entendendo Services

- **ClusterIP:** Se comunica de forma interna.

- **NodePort:**  Se comunica de forma externa.

- **LoadBalancer:** Se comunica de forma externa atraves do provedor de nuvem.

## Comandos utilizados

* Comando para criar: Deployment

```
kubectl apply -f deployment.yaml
```

* Comando para criar: ClusterIP, NodePort, LoadBalancer

```
kubectl apply -f serviceClusterIP.yaml
kubectl apply -f serviceNodePort.yaml
kubectl apply -f serviceLoadBalancer.yaml
```

* Comando para criar 1 Service NodePort de maneira rápida na linha de comando e incluir em um arquivo yaml

```
kubectl expose deploy api -o yaml --type=NodePort --port=80 > serviceNodePort.yaml
```

* Comando para acessar pelo ClusterIP

```
curl http://api-service:80/temperatura/fahrenheitparacelsius/100
```

* Comando para acessar pelo NodePort

```
curl http://192.168.0.8:32167/temperatura/fahrenheitparacelsius/100
```

## Pontos importantes

O **targetPort** é a porta do container.
O **port** é a porta do service.