# Aplicação Jogo da Velha

Este repositório contem um jogo da velha que permite você salvar o jogo quando houver um ganhador.

Os seguintes módulos e ferramentas foram utilizados para o desenvolvimento da aplicação:

Módulo para manter o servidor funcionando: https://github.com/remy/nodemon

Framework para rotas REST: https://github.com/restify/node-restify

Módulo ORM para Mysql: https://github.com/tgriesser/knex, http://knexjs.org

## Instalação e execução

Para testar a aplicação, você deve ter o MySQL instalado, com a estrutura de banco de dados e tabela já criados. Você pode executar o script a seguir para gerar esta estrutura!

```sql
CREATE DATABASE IF NOT EXISTS `db` ;
USE `db` ;

CREATE TABLE IF NOT EXISTS `db`.`velha` (
  `id` INT(11) NOT NULL AUTO_INCREMENT,
  `jogadorX` VARCHAR(30) NULL DEFAULT NULL,
  `jogadorO` VARCHAR(30) NULL DEFAULT NULL,
  `jogadas` VARCHAR(30) NULL DEFAULT NULL,
  `img` TEXT NULL DEFAULT NULL,
  PRIMARY KEY (`id`))
ENGINE = InnoDB

```

No arquivo index.js, troque os valores de configuração do MySQL por aqueles utilizados por você.

```javascript
var knex = require('knex')({
  client: 'mysql',
  connection: {
    host : 'seu_host',
    user : 'seu_usuario',
    password : 'sua_senha',
    database : 'seu_banco'
    }
});
```

Acesse o terminal e execute o comando `npm i -g nodemon` para instalar o nodemon como global.

Em seguida, dentro da pasta do projeto, execute

```
npm install
```

Após concluída a instalação, execute o comando `nodemon index.js`