# como utilizar o eslint

* vamos iniciar instalando o eslint em nosso projeto.
* se você estiver usando npm ```npm init @eslint/config```
* se você estiver usando yarn ```yarn init @eslint/config```
* se você estiver usando pnpm ```pnpm init @eslint/config```

__os comandos acima fornecem uma instalação rapida.__

* também é possivel instalar utilizando o comando ```install``` ou ```i```

__no explo abaixo estou instalando o eslint junto com as configurações @rocketseat .__

* pnpm: ```pnpm add eslint @rocketseat/eslint-config```

## apos instalação

caso você tenha feito a isntalação atraves do yarn ou npm é bem provavel que o arquivo ```.eslintrc``` tenha sido criado na raiz da sua aplicação.

caso não tenha, criaremos manualmente este arquivo.

* o arquivo ```.eslintrc``` suporta formatos ```{.js, .json. yaml}```
__abaixo utilizaremos ```.eslintrc.json``` .__

* com o arquivo ```.eslintrc.json``` criado, utilizamos as seguintes configurações:

```json

{
  "env": {
      "browser": true,
      "es2021": true
  },
  "extends": "eslint:recommended",
  "parserOptions": {
      "ecmaVersion": "latest",
      "sourceType": "module"
  },
}
```

* caso você tenha criado o arquivo ```{.js}```

```json
module.exports = {
  "env": {
      "browser": true,
      "es2021": true
  },
  "extends": "eslint:recommended",
  "parserOptions": {
      "ecmaVersion": "latest",
      "sourceType": "module"
  },
}
```

* como optei por utilizar a configuração da ```@rocketseat``` então precisamos passar algumas configurações.

* em ```json {"extends": }``` passaremos o valor:  

```json
{"extends": ["@rocketseat/eslint-config/node"]}

```

* mas de onde veio esta configuração?

* após a instalação do pacote ```@rocketseat/eslint-config``` podemos olhar dentro de nossa pasta ```node_modules/```

```shell
. <-- nossa pasta raiz
  ├── node_modules/
      └── @rocketseat
          ├── next.js
          ├── node.js
          ├── react.js
          ├── Readme.md
```

* navegando entre os diretorios, encontramos a estrutura de pastas acima contendo 3 arquivos
```next.js```,
```node.js```,
```react.js```

* estes arquivos é o que chamaremos em `@rocketseat/eslint-config/{'o arquivo desejado'}`

* caso fique em duvida, você também encontra um ```README.MD``` que pode ajudar a entender melhor cada configuração.

## configuração package.json

* em scripts adicionamos:

```json
"lint": "eslint src --ext .ts --fix"
```

>* informando a "extensão dos arquivos" que queremos formatar
>
> ```json
> --ext .ts
> ```
>
> caso tenha mais arquivos em sua aplicação pode-se adicionar em fileira ex: ```--ext .ts, .tsx, .js```.

>* informando ao eslint que ele pode concertar todos os erros que encontrar automaticament
>
> ```json
> --fix
> ```

* por ultimo, tenha sempre instalado a extensão: [Eslint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint) em seu vscode
