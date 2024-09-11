# Encontros do Módulo 07 do Curso de Engenharia da Computação (Inteli)

Este repositório possui os materiais de estudo, códigos e slides referentes a parte de Kubernetes do Módulo 10, cuja temática é **Sistemas de Manutenção Preditiva**.


## Encontros
<details>
  <summary>Encontro 03 - Docker</summary>

  <br/>

  **Roteiro do Lab:**

  1. Execute o comando:

  ```docker run hello-world```

  Este comando irá:
  - Procurar a imagem hello-world localmente.
  - Se não encontrar, fará o download do Docker Hub.
  - Criará um contêiner a partir da imagem e o executará.
  - Exibirá a mensagem "Hello from Docker!" no terminal.

  2. Verifique as imagens:

  ```docker images```

  Você verá a imagem hello-world listada. O comando docker images lista todas as imagens Docker baixadas em seu sistema. Cada imagem possui:
  - REPOSITORY: Nome do repositório da imagem (ex: hello-world, nginx).
  - TAG: Versão da imagem (ex: latest, 1.23.4).
  - IMAGE ID: Identificador único da imagem.
  - CREATED: Data de criação da imagem.
  - SIZE: Tamanho da imagem.

  3. Execute o comando:

  ```docker run -d -p 80:80 nginx:latest```

  Este comando irá:
  - Baixar a imagem nginx:latest do Docker Hub se ela não existir localmente.
  - Criar um contêiner em segundo plano (-d) e encaminhar a porta 80 do host para a porta 80 do contêiner (-p 80:80).

  4. Acesse o servidor Nginx:

  Abra um navegador e acesse ```http://localhost```. Você verá a página padrão do Nginx.

  5. Crie um arquivo chamado docker-compose.yml com o seguinte conteúdo:

  ```
  version: "3.9"
  services:
    postgres:
      image: postgres:latest
      environment:
        POSTGRES_USER: usuario
        POSTGRES_PASSWORD: senha
        POSTGRES_DB: meu_banco
      volumes:
        - db_data:/var/lib/postgresql/data
  volumes:
    db_data:
  ```

  6. No mesmo diretório do arquivo docker-compose.yml, execute o comando:

  ```docker-compose up -d```