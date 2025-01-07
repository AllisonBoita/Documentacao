# 📅 Resumo do Dia 7 - Configurando o Watch Mode

Faz com que não precise ser compilado a cada **save**. Ele compila e atualiza automaticamente.

Crie o **tsconfig.json** com as configurações previamente feitas.

## 🚀 Ativando o Watch Mode

Para ativar o watch mode, use o comando:

`tsc --watch`

A alteração pode ser feita para mais de um arquivo **TS** ao mesmo tempo. Basta alterar e, claro, apontar no **index** para que o compilador o enxergue.

## 🔧 Selecionando Arquivos que Desejo Compilar

Você pode optar por realizar o **Include** ou o **Exclude** de arquivos que quer ou não que o watch mode enxergue.

Se você deseja que dentro do seu projeto com 4 arquivos ele compile apenas 1, é mais fácil incluí-lo do que remover os outros 3.

No final do arquivo **tsconfig.json**, adicione o **exclude**, por exemplo:

`"exclude": [ "code/compiler.ts" ]`

## 🖥️ Trabalhando com Target

**Language and Environment**  
`"target": "es2016", /* Set the JavaScript language version for emitted JavaScript and include compatible library declarations. */`

Ele serve para definir qual versão está sendo usada para compilar o **JS**. Isso também vai depender da versão do navegador utilizada.

Para isso, podemos verificar na internet qual versão do **JavaScript** o navegador suporta.

[https://www.whatismybrowser.com/detect/ecma-script-version/](https://www.whatismybrowser.com/detect/ecma-script-version/)

## 🐞 Habilitando o Source Map - Debug

No **TSConfig.json**:

`"sourceMap": true, /* Create source map files for emitted JavaScript files. */`

Quando ele é habilitado, ele cria um arquivo de mapeamento que o **browser** consegue ler.

Ao ativar a configuração e compilar novamente, ele cria um arquivo `.map`.

## 📝 Comentários - Deixar ele apenas no arquivo .ts

`"removeComments": true, /* Disable emitting comments. */`

Habilitando esta opção, os comentários feitos no arquivo `.ts` não são compilados junto ao arquivo `.js`.

## 📂 RootDir e OutDir

A pasta de código criada normalmente é chamada de **src**.

A pasta de produção normalmente é chamada de **dist**.

O **RootDir** informa onde os arquivos `.ts` são criados, enquanto o **OutDir** retorna onde os arquivos são salvos.

## ⚠️ No Emit On Error

Quando existe um erro de código, ele me retorna o erro e não compila o arquivo para o `.js`.

`"noEmitOnError": true,   /* Disable emitting files if any type checking errors are reported. */`

## 🔍 Type Checking

`"strict": true,    /* Enable all strict type-checking options. */`  
`"noImplicitAny": true,  /* Enable error reporting for expressions and declarations with an implied 'any' type. */`

O `strict` habilitado faz com que todas as configurações do grupo sejam habilitadas.

```typescript
    // "strictNullChecks": true,                         /* When type checking, take into account 'null' and 'undefined'. */
    // "strictFunctionTypes": true,                      /* When assigning functions, check to ensure parameters and the return values are subtype-compatible. */
    // "strictBindCallApply": true,                      /* Check that the arguments for 'bind', 'call', and 'apply' methods match the original function. */
    // "strictPropertyInitialization": true,             /* Check for class properties that are declared but not set in the constructor. */
    // "strictBuiltinIteratorReturn": true,              /* Built-in iterators are instantiated with a 'TReturn' type of 'undefined' instead of 'any'. */
    // "noImplicitThis": true,                           /* Enable error reporting when 'this' is given the type 'any'. */
    // "useUnknownInCatchVariables": true,               /* Default catch clause variables as 'unknown' instead of 'any'. */
    // "alwaysStrict": true,                             /* Ensure 'use strict' is always emitted. */
```

## 🚫 NoImplicitAny

O `NoImplicitAny` não permite que variáveis do tipo `ANY` sejam utilizadas.

---

## 🧹 Utilizando o Unused Locals

`"noUnusedLocals": true, /* Enable error reporting when local variables aren't read. */`

Utilizada quando eu declaro uma variável e não uso ela.

Ao tentar executar, ele me informa que, caso haja, a variável não está sendo utilizada.

É claro que ele só valida dentro da função. Se eu usar ela fora, o "alerta" não é exibido.

---

## 🧹 Utilizando o Unused Parameters

`"noUnusedParameters": true, /* Raise an error when a function parameter isn't read. */`

Basicamente valida se é usada ou não, assim como a **Locals**, porém valida parâmetros de uma função.

---

## 🚷 No Implicit Returns

`"noImplicitReturns": true, /* Enable error reporting for codepaths that do not explicitly return in a function. */`

Ele valida se existe um retorno adequado para todos os **paths**.

Exemplo:

```typescript
function productPrice(price: number, currency: string) {
    if (price > 20) {
        return price;
    }
}
```