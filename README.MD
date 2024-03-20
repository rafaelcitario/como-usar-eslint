# Como usar o Eslint

## Instalando ESLint no seu projeto

Vamos começar instalando o ESLint em nosso projeto. 

Se estiver utilizando npm:

```bash
npm init @eslint/config
```

Para usuários do Yarn:

```bash
yarn init @eslint/config
```

E para os que preferem o pnpm:

```bash
pnpm init @eslint/config
```

Esses comandos fornecem uma instalação rápida.

Também é possível instalar utilizando o comando 

**`install`**
ou 
**`i`**.

No exemplo abaixo, estou instalando o ESLint junto com as configurações da Rocketseat:

Para pnpm:

```bash
pnpm add eslint @rocketseat/eslint-config
```

## Após a instalação

Caso você tenha feito a instalação através do Yarn ou npm, é bem provável que o arquivo `.eslintrc` tenha sido criado na raiz da sua aplicação. 
Caso não tenha sido criado, podemos fazer isso manualmente.

O arquivo **`.eslintrc`** suporta os formatos **`.js`**, **`.json`**, **`.yaml`**. 

Abaixo, utilizaremos **`.eslintrc.json`**.

Com o arquivo **`.eslintrc.json`** criado, utilizamos as seguintes configurações:

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
  }
}
```

Caso você tenha optado por utilizar a configuração da Rocketseat, precisamos passar algumas configurações. 

Em **`"extends"`**, passaremos o valor:

```json
{"extends": ["@rocketseat/eslint-config/node"]}
```

Mas de onde veio essa configuração?

Após a instalação do pacote **`@rocketseat/eslint-config`**, podemos olhar dentro da nossa pasta **`node_modules/`**. 
Navegando entre os diretórios, encontramos a estrutura de pastas acima contendo três arquivos: **`next.js`**, **`node.js`**, **`react.js`**. 
Estes arquivos são o que chamaremos em **`@rocketseat/eslint-config/{arquivo_desejado}`**. 
Caso fique em dúvida, você também encontra um **`README.md`** que pode ajudar a entender melhor cada configuração.

## Configuração no package.json

Em scripts, adicionamos:

```json
"lint": "eslint src --ext .ts --fix"
```

Informando a extensão dos arquivos que queremos formatar:

```json
--ext .ts
```

Caso tenha mais tipos de arquivos em sua aplicação, você pode adicionar em sequência, por exemplo: **`--ext .ts, .tsx, .js`**. 
Também informamos ao **ESLint** que ele pode corrigir todos os erros que encontrar automaticamente:

```json
--fix
```

Por último, tenha sempre instalada a extensão [ESLint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint) em seu VSCode.
