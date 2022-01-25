# Deployment

* Aplicando deploy

```bash
kubectl apply -f primeiro-deployment.yaml -f segundo-deployment.yaml -f terceiro-deployment.yaml
```

**OBS:** No terceiro-deployment.yaml temos a opção de **nodeSelector** que irá adicionar o novo deploy no node que conter a configuração descrita com a label **SSD** . 


* Labels - Mostrando todos os labels que existem nos nodes

```bash
kubectl label nodes node2 --list
kubectl label nodes node3 --list
```

* Labels - Adionando um novo label no node

```bash
kubectl label nodes node2 disk=SSD
kubectl label nodes node3 disk=HDD
```

* Labels - Alterar conteúdo do label existente no node

```bash
kubectl label nodes node2 --overwrite disk=HDD
```

* Labels - Removendo label do node

```bash
kubectl label nodes disk- --all
kubectl label nodes node2 --list
```

* Labels - Identificando label usado nos pods

```bash
kubectl get po -L dc
```

* Labels - Filtrando de forma isolada o pod, atraves da label

```bash
kubectl get po -l dc=BR
``` 