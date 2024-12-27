## Resumo do Dia 5: Tipagem Estática vs. Dinâmica e Conversões de Tipo em JavaScript

No quinto dia, exploramos a distinção entre linguagens de programação com tipagem estática e dinâmica, e mergulhamos nas conversões de tipo em JavaScript, uma linguagem de tipagem dinâmica. Abordamos como converter entre strings, números e booleanos. Vamos detalhar esses conceitos:

### 1. Linguagens de Programação Estáticas vs. Dinâmicas
Tipagem Estática: Em linguagens com tipagem estática, o tipo de cada variável é conhecido em tempo de compilação. Isso significa que você deve declarar o tipo de dado que uma variável vai armazenar e esse tipo não pode mudar. Exemplos incluem C, C++ e Java.

Tipagem Dinâmica: Linguagens com tipagem dinâmica, como JavaScript, permitem que o tipo de uma variável possa mudar em tempo de execução. Você não precisa declarar o tipo da variável antecipadamente, e o mesmo espaço de memória pode armazenar dados de tipos diferentes em momentos diferentes.

### 2. Convertendo String para Número
Em JavaScript, podemos converter strings em números para realizar operações matemáticas. Existem várias maneiras de fazer isso:

parseInt(string): Converte a string para um número inteiro.

Exemplo: parseInt("123") // Resultado: 123

parseFloat(string): Converte a string para um número de ponto flutuante (com decimais).

Exemplo: parseFloat("123.45") // Resultado: 123.45

Operador Unário +: Colocar um + antes de uma string a converte em número.

Exemplo: +"123" // Resultado: 123

### 3. Convertendo Número para String

A conversão de números para strings é útil quando precisamos de uma representação textual do número, por exemplo, ao concatenar com outra string.

Método toString(): Todo número tem esse método, que retorna sua forma string.

Exemplo: (123).toString() // Resultado: "123"

Template Literals: Usar o número dentro de um template literal também realiza a conversão.

Exemplo: `${123}` // Resultado: "123"

### 4. Convertendo Número para Boolean

A conversão para boolean é importante em contextos condicionais, onde valores truthy e falsy desempenham um papel crucial.

Regra Geral: Em JavaScript, 0, NaN (Not a Number) e o número null são considerados falsy e serão convertidos para false. Qualquer outro número é truthy e será convertido para true.

Operador Boolean(): Explicitamente converte um número para boolean.

Exemplo: Boolean(123) // Resultado: true

Exemplo: Boolean(0) // Resultado: false

### Considerações Importantes

A conversão entre tipos é uma prática comum em JavaScript devido à sua natureza de tipagem dinâmica. No entanto, é essencial entender como essas conversões funcionam para evitar resultados inesperados.

Testar e experimentar com diferentes tipos e métodos de conversão pode ajudar a solidificar sua compreensão desses conceitos.

Neste dia, adquirimos uma compreensão mais profunda sobre a flexibilidade do JavaScript com tipos de dados e exploramos técnicas para converter entre diferentes tipos. Essas habilidades são fundamentais para manipular dados e criar lógicas condicionais eficazes em seus programas. Pratique essas conversões para se familiarizar com elas e, como sempre, estou aqui para ajudar com qualquer dúvida ou para explorar mais exemplos!