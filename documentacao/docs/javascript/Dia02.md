## Variáveis
O que são: Variáveis são contêineres para armazenar valores de dados. Elas nos permitem etiquetar dados com um nome descritivo para facilitar a referência e manipulação no código.

### Como declarar:

var: A forma mais antiga de declarar variáveis. Tem escopo de função e pode ser redeclarada e atualizada.

let: Introduzido no ES6 (ECMAScript 2015), permite a declaração de variáveis com escopo de bloco, o que significa que a variável só existe dentro do bloco onde foi declarada. Pode ser atualizada, mas não redeclarada no mesmo escopo.

Exemplo: let mensagem = "Olá, mundo!";

## Manipulação de Variáveis

Operações: Uma vez declaradas, as variáveis podem ser manipuladas e ter seus valores atualizados. Podemos realizar operações matemáticas com variáveis numéricas, concatenar strings, entre outras manipulações.

## Constantes

O que são: Constantes são semelhantes às variáveis, mas uma vez atribuído um valor, ele não pode ser alterado. Isso é útil para valores que sabemos que não precisarão ser modificados ao longo do nosso programa.

Como declarar:

const: A palavra-chave const é usada para declarar constantes. Assim como let, tem escopo de bloco e não pode ser redeclarada ou atualizada.

Exemplo: const PI = 3.14;

## Boas Práticas

Preferir let e const em detrimento de var para declarar variáveis, devido ao escopo de bloco mais previsível e à prevenção de redeclarações acidentais.

Usar const para valores que sabemos que não mudarão, como URLs de API, valores de configuração, etc., para garantir a imutabilidade desses valores no código.