Aqui está o texto corrigido sem alterar a formatação:

# Como utilizar o ESLint

Vamos iniciar instalando o ESLint em nosso projeto.
Se você estiver usando **NPM** 
```npm init @eslint/config```

Se você estiver usando **YARN** 
```yarn init @eslint/config```

Se você estiver usando **PNPM** 
```pnpm init @eslint/config```

__Os comandos acima fornecem uma instalação rápida.__

Também é possível instalar utilizando o comando 
```install```
ou
```i```

__No exemplo abaixo estou instalando o ESLint junto com as configurações @rocketseat .__

**PNPM**: ```pnpm add eslint @rocketseat/eslint-config```

## Após a instalação

Caso você tenha feito a instalação através do Yarn ou npm, é bem provável que o arquivo ```.eslintrc``` tenha sido criado na raiz da sua aplicação.

Caso não tenha, criaremos manualmente este arquivo.

O arquivo ```.eslintrc``` suporta formatos 
```json

{
 .js,
 .json, 
 .yaml
}

```
__Abaixo utilizaremos ```.eslintrc.json``` .__

Com o arquivo ```.eslintrc.json``` criado, utilizamos as seguintes configurações:

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

Caso você tenha criado o arquivo ```{.js}```

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

Como optei por utilizar a configuração da ```@rocketseat``` então precisamos passar algumas configurações.

Em 

```json

{"extends": }

```

Passaremos o valor:  

```json
{"extends": ["@rocketseat/eslint-config/node"]}

```

Mas de onde veio esta configuração?

Após a instalação do pacote ```@rocketseat/eslint-config``` podemos olhar dentro de nossa pasta ```node_modules/```


```shell
. <-- nossa pasta raiz
  ├── node_modules/
      └── @rocketseat
          ├── next.js
          ├── node.js
          ├── react.js
          ├── Readme.md
```

Navegando entre os diretórios, encontramos a estrutura de pastas acima contendo 3 arquivos
```next.js```,
```node.js```,
```react.js```

Estes arquivos é o que chamaremos em `@rocketseat/eslint-config/{'o arquivo desejado'}`

Caso fique em dúvida, você também encontra um ```README.MD``` que pode ajudar a entender melhor cada configuração.

## configuração package.json

Em scripts adicionamos:

```json
"lint": "eslint src --ext .ts --fix"
```

> informando a "extensão dos arquivos" que queremos formatar
>
> ```json
> --ext .ts
> ```
>
> caso tenha mais arquivos em sua aplicação pode-se adicionar em fileira ex: ```--ext .ts, .tsx, .js```.

> informando ao eslint que ele pode corrigir todos os erros que encontrar automaticamente
>
> ```json
> --fix
> ```

 Por último, tenha sempre instalada a extensão: [ESLint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint) em seu VSCode
