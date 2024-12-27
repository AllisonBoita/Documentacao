## Resumo do Dia 4: Tipos de Dados, Dados Primitivos e Dados de Referência em JavaScript

No quarto dia da nossa jornada em JavaScript, aprofundamos nosso entendimento sobre os tipos de dados disponíveis na linguagem, diferenciando entre dados primitivos e dados de referência. Vamos revisar os conceitos-chave:

## Tipos de Dados em JavaScript

JavaScript categoriza os valores em dois grandes grupos: tipos primitivos e tipos de referência. Entender essa divisão é fundamental para manipular dados de forma eficaz em nossos programas.

### Dados Primitivos

São os tipos de dados mais básicos da linguagem e têm a característica de serem imutáveis. Quando você manipula um valor primitivo, você está criando um novo valor. Os principais tipos primitivos em JavaScript são:

String: Sequências de caracteres, usadas para representar texto. Ex.: "Olá, mundo!".

Number: Representa tanto números inteiros quanto de ponto flutuante. Ex.: 42, 3.14.

BigInt: Para números inteiros muito grandes que o tipo Number não pode representar.

Boolean: Tem dois valores possíveis, true ou false, usado para lógicas de verdadeiro ou falso.

Undefined: Indica que uma variável foi declarada mas ainda não foi atribuído um valor.

Null: Representa a intencional ausência de valor de objeto.

Symbol: Introduzido no ES6, representa valores únicos que não são iguais a nenhum outro valor.

### Dados de Referência (Objetos)

Ao contrário dos tipos primitivos, os dados de referência (ou objetos) são coleções de propriedades, e ao manipular esses dados, você está trabalhando com referências a um espaço na memória onde esses dados estão armazenados. Isso inclui:

Objetos: Coleções de pares chave-valor. Ex.: { nome: "João", idade: 30 }.

Arrays: Listas ordenadas de valores. Ex.: [1, 2, 3, "texto"].

Funções: Blocos de código reutilizáveis. Ex.: function cumprimentar() { console.log("Olá!"); }.

### Comportamento na Atribuição e Passagem

Dados Primitivos: Quando você atribui ou passa tipos primitivos, é feita uma cópia do valor. Isso significa que se você alterar o valor posteriormente, a cópia original não será afetada.

Dados de Referência: Ao atribuir ou passar objetos, arrays ou funções, você está passando uma referência ao objeto original. Isso significa que se você modificar o objeto através de uma das referências, todas as outras referências verão a mudança.

### Considerações Importantes

O entendimento da diferença entre tipos primitivos e de referência é crucial para evitar efeitos colaterais indesejados em seu código, especialmente ao trabalhar com funções e métodos que alteram os dados passados a eles.

Ao trabalhar com dados de referência, métodos como Object.assign() ou o operador de espalhamento ... podem ser usados para criar cópias de objetos, evitando a modificação do objeto original.

Este dia foi dedicado a estabelecer uma compreensão sólida dos fundamentos dos tipos de dados em JavaScript. Compreender essas diferenças é essencial para manipular corretamente os dados em nossos programas e evitar bugs. Experimente com esses conceitos em seu código e observe como os diferentes tipos de dados se comportam. Estou aqui para qualquer esclarecimento ou para explorar mais exemplos juntos!
