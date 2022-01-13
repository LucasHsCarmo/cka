# Limitando Recursos

- Especificando o limite de recursos de CPU e memória usado no **deployment.yaml** a seguir:

```
...
resources:
  limit:
    cpu: "500m"
    memory: 512Mi 
  requests:
    cpu: "500m"
    memory: 256Mi
...
```

- **Objeto limitranges:** Especificando o limit com **limitando-recursos.yaml** em um namespace isolado **giropops** , sendo assim, a cada Pod criado dentro desse contexto, terá automaticamente o limite de cpu e memória é adicionado.

## Comandos utilizados

- Comando para criar contetxo: giropops

```
kubectl create namespace giropops
```

- Comando para criar: Deployment (detalhe com contexto já add no yaml)

```
kubectl apply -f deployment.yaml
```

- Comando para criar: Pod

```
kubectl apply -f pod-limit-range.yaml -n giropops
```

- Comando para listar todos os objetos criados dentro do contexto giropops

```
kubectl get all -n giropops
```