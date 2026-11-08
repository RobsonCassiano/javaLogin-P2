# javaLoginP2

Aplicação desktop de cadastro e gerenciamento de usuários, feita em Java 17 com Swing, Maven e MySQL.

## Pré-requisitos

- JDK 17 ou superior;
- Maven;
- MySQL em execução.

## Preparar o banco de dados

Execute o conteúdo completo de [`banco.sql`](./banco.sql) no MySQL. O script cria o banco e a tabela caso ainda não existam e configura o campo de usuário para diferenciar maiúsculas de minúsculas. Se a tabela já existia, o script também atualiza a collation dessa coluna sem apagar os dados.

O nome de usuário deve ser informado exatamente como foi cadastrado: por exemplo, `Maria` e `maria` são usuários diferentes.

Se sua instalação usa outras credenciais ou endereço, ajuste os valores privados de conexão em `src/main/java/login/Conexao.java`.

As senhas são gravadas pelo MySQL com `MD5`, conforme o esquema solicitado.

## Compilar e executar

Na raiz do projeto:

```shell
mvn clean package
mvn exec:java "-Dexec.mainClass=login.Main"
```

Também é possível abrir o projeto em uma IDE Maven e executar a classe `login.Main`, que inicia a tela de login.
