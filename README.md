# Meat - Angular App Starter

## 1. Passos para começar

### Clonando o Repositório

`git clone https://github.com/cod3rcursos/meat-app-starter.git`

### Instalando as Dependências

`npm install`

### Inicializando o Servidor

`ng serve` ou `npm start`

## 2. Iniciando o Backend

### Instalando o json-server

`npm install -g json-server`

### Iniciando o serviço (raiz da aplicação)

`json-server db.json`

## Goodies

Expressões regulares usadas na validação de formulários

### Email Regex

`/^(([^<>()\[\]\.,;:\s@\"]+(\.[^<>()\[\]\.,;:\s@\"]+)*)|(\".+\"))@(([^<>()[\]\.,;:\s@\"]+\.)+[^<>()[\]\.,;:\s@\"]{2,})$/i`

### Number Regex

`/^[0-9]*$/`

## Upgrade para Angular 4.3

Dependências dos pacotes que devem ficar em package.json:

```
"dependencies": {
    "@angular/animations": "4.3.3",
    "@angular/common": "4.3.3",
    "@angular/compiler": "4.3.3",
    "@angular/core": "4.3.3",
    "@angular/forms": "4.3.3",
    "@angular/platform-browser": "4.3.3",
    "@angular/platform-browser-dynamic": "4.3.3",
    "@angular/router": "4.3.3",
    "admin-lte": "2.3.11",
    "core-js": "2.4.1",
    "font-awesome": "4.7.0",
    "intl": "1.2.5",
    "jquery": "3.1.1",
    "reflect-metadata": "0.1.10",
    "rxjs": "5.4.2",
    "ts-helpers": "1.1.2",
    "web-animations-js": "2.2.5",
    "zone.js": "0.8.16"
  },
  "devDependencies": {
    "@angular/cli": "1.2.7",
    "@angular/compiler-cli": "4.3.3",
    "@types/jasmine": "2.5.53",
    "@types/express": "4.0.37",
    "@types/jsonwebtoken": "7.2.3",
    "@types/node": "7.0.5",
    "codelyzer": "3.1.2",
    "jasmine-core": "2.7.0",
    "jasmine-spec-reporter": "4.1.1",
    "json-server": "0.12.0",
    "jsonwebtoken": "7.4.1",
    "karma": "1.7.0",
    "karma-chrome-launcher": "2.2.0",
    "karma-cli": "1.0.1",
    "karma-jasmine": "1.1.0",
    "karma-remap-istanbul": "0.6.0",
    "protractor": "5.1.2",
    "ts-node": "3.3.0",
    "tslint": "5.5.0",
    "typescript": "2.4.2",
    "webdriver-manager": "12.0.6"
  }
```
## Créditos

Todas as imagens usadas na aplicação são pertencentes a freepik.com

## specs implementadas por animations
CSS3 TRANSITIONS
w3.org/TR/css3-transitions/#animable-properties

CSS3 ANIMATIONS

## Construindo a aplicação
# usa configurações de desenvolvimento
ng build
`gera arquivos .map, que permite debugar
 também gera erros javascript (como falta de propriedades), que não são geradas ao executar ng serve
`

# usa configurações de produção
ng build --prod

## Publicando no Apache HTTP
# estratégia de hash (não precisa configurar nada)
- precisa do provider {provide: LocationStrategy, useClass: HashLocationStrategy}
Levar o conteúdo da pasta dist para a pasta e colocar na pasta do apache onde tem o index.html

# estratégia de caminho
- remover o provider {provide: LocationStrategy, useClass: HashLocationStrategy}
- fazer novo build de produção
- deletar os arquivos (da instalação por hash)
- colar o conteúdo do dist gerado no build
- mostra o passo a passo do site do angular io (seção production servers)
-- nesse link, recomenda colocar a configuração no arquivo htaccess, mas na doc do apache, manda colocar no arquivo principal (httpd.conf)
-startar o apache
- ativar o módulo rewrite_module no arquivo httpd.configura
