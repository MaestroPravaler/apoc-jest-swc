# Verificação do Jest e do SWC

## 01 - Criação de um projeto com NestJS

``` bash
nest new nestjs-jest-swr
```

## 02 - Rodar o teste padrão do projeto

- Resultado:
  ![Jest](/assets/images/jest.png)

## 03 - Instalar e configurar o SWC

``` bash
npm install @swc/core @swc/jest --save-dev
```

- No arquivo package.json, adicionar a seguinte configuração:

```  yaml
"jest": {
    "transform": {
      "^.+\\.(t|j)sx?$": "@swc/jest"
    }
  }
```

- Criar um arquivo na raiz do projeto .swcrc com o seguinte conteúdo:

``` json
{
  "jsc": {
    "parser": {
      "syntax": "typescript",
      "tsx": true,
      "decorators": true
    },
    "target": "es2017",
    "keepClassNames": true,
    "transform": {
      "legacyDecorator": true,
      "decoratorMetadata": true
    }
  }
}

```

- Rodar o teste com o SWC

- Resultado:
  ![swc](/assets/images/swc.png)

## 04 - configuração Extra

Instalar o Plugin do Jest para VSCode (Jest Runner). Com ele conseguimos rodar os testes diretamente do arquivo de testes

- Resultado:
  ![jest-plugin](/assets/images/jest-plugin.png)
