# Daemonset

Um DaemonSet garante que todos (ou alguns) nós executem uma cópia de um pod. À medida que os nós são adicionados ao cluster, os pods são adicionados a eles. À medida que os nós são removidos do cluster, esses pods são coletados como lixo. A exclusão de um DaemonSet limpará os pods que ele criou.

* Criando o daemonset

```bash
kubectl apply -f primeiro-daemonset.yaml
```

* Validando o daemonset criado

```bash
kubectl get ds
```

* Validando os pods criados através do daemonset

```bash
kubectl get po -o wide
```

* Alterando a imagem do pod

```bash
kubectl set image ds primeiro-daemonset nginx=nginx:1.15.0
```