# Encontros do Módulo 07 do Curso de Engenharia da Computação (Inteli)

Este repositório possui os materiais de estudo, códigos e slides referentes a parte de Kubernetes do Módulo 10, cuja temática é **Sistemas de Manutenção Preditiva**.


## Encontros
<details>
  <summary>Encontro 03 - Docker</summary>

  <br/>

  **Roteiro do Lab:**



  Este Lab irá apresentar o conceito de Deployment e do ReplicaSet dentro do Kubernetes.

  > **Dica:** É bom trabalhar em pequenos grupos para discutir como adaptar os Deployments para o Projeto do Módulo.

  > **Dica:** Certifique-se de que o Minikube esteja no ar antes de começar o Lab, na dúvida, execute o comando `minikube start` no seu Terminal.

  1. Vamos começar realizando um Deployment (se não está confiante de como funciona, veja os slides da instrução à respeito), neste caso, de uma Pod contendo o Nginx e com 3 réplicas. Segue o arquivo de Deployment de nome `nginx-deployment.yaml`.

  ```
  apiVersion: apps/v1
  kind: Deployment
  metadata:
    name: nginx-deployment
    labels:
      app: nginx
  spec:
    replicas: 3
    selector:
      matchLabels:
        app: nginx
    template:
      metadata:
        labels:
          app: nginx
      spec:
        containers:
        - name: nginx
          image: nginx:1.14.2
          ports:
          - containerPort: 80
  ```
  > **Pergunta:** Analise esse YAML e verifique que configurações estão sendo realizadas por meio desse Deployment.

  > **Dica:** Salve todos os arquivos YAML em uma mesma pasta para ter todos os arquivos em um local só, vai facilitarr para usar o `kubectl` ao longo do Lab.
