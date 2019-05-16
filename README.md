#1 - Clonar o Projeto
- Verifica se o PHP7.2 tá disponível no Wamp
- Verifica se a versão do MySQL é a 5.7.26
- Extrair a pasta Vendor de dentro do arquivo Vendor.zip
- Colocar o arquivo .env na sua raiz

#2 - Adicionar o PHP e o MySQL às variaveis de ambiente
- Menu Iniciar
- Procura por "Variáveis de Ambiente"
- No quadro de cima, clica duas vezes em **Path** e vai aparecer uma lista
- Adiciona **"C:\wamp64\bin\php\php7.2.18"**
- Adiciona **"C:\wamp64\bin\mysql\mysql5.7.26\bin"**

#3 - Extensões do PHP
- Baixa o **php_zip.dll**
- Abre C:/wamp/bin/php/ext/ e coloca ele lá dentro
- Abre o Wamp, com o botão esquerdo
- Vai em PHP -> PHP.ini e abre em um editor
- Dentro dele, procura por **extension=curl**
- Se tiver com um **;** na frente, remove o **;**
- Tem várias extensions, então la embaixo da última, adiciona também **extension=zip**

#4 - Banco de Dados
### Criar DB
- Vai no Wamp, com o botão esquerdo
- Abre o terminal do Windows
- Digita o comando ``mysql -uroot -p``
- Aí quando logar você executa:
    ```
    create database maximo_db;
    exit;
    ```

### Exportar DB
No terminal, o comando abaixo vai gerar um arquivo chamado **maximo_db.sql** no local onde você executar.
```
mysqldump maximo_db -uroot -p > maximo_db.sql
```
### Importar DB
Utilizando um arquivo .sql existente, no caso, **maximo_db.sql**, roda o comando
```
mysql -uroot -p maximo_db < maximo_db.sql
```

#5 - Configurar VirtualHost
- No Wamp, com o botão esquerdo, vá até Your VirtualHosts
- VirtualHost Management
- No campo "Name of the Virtual Host", coloque o dominio que deseja, eu to usando **dev.maximo**
- no Campo abaixo, "Complete Absolute Path", fica: "C:/wamp64/www/nome-da-pasta-onde-tu-clonou/web"
- Depois pode ignorar o ultimo campo e clicar no "Start The Creation of The Virtual Host".
- Você vai precisar reiniciar os serviços depois disso
- Wamp, com botão esquerdo -> Restart All services;

#6 - Rodando o Craft
- No terminal, na raiz do projeto, executa ```php craft/setup```
- Por padrao ele pega as configs do .env, entao é só dar enter pra tudo
- Depois é só rodar e ver se rolou!

#7 - Outros
- Talvez você precise ter o **composer** instalado na sua máquina também.
