# 📅 Resumo do Dia 8: Template Literals, Métodos e Objetos em JavaScript

No oitavo dia, mergulhamos em técnicas avançadas para manipular strings e números, exploramos a utilidade dos métodos matemáticos e a criação dinâmica de objetos em JavaScript. Esse conhecimento enriquece nossa caixa de ferramentas de programação, permitindo-nos escrever código mais expressivo e eficiente.

---

## Tópicos Discutidos

### 1. 💬 Utilizando Template Literals
**Template literals** (ou **template strings**) são uma forma elegante e poderosa de incorporar expressões dentro de strings, facilitando a criação de strings complexas sem a necessidade de concatenação.

- **Sintaxe**: Usam crases (`` ` ``) ao invés de aspas simples ou duplas e permitem a interpolação de expressões usando `${expressao}`.

Ex:  
`let nome = "Ana";`  
`let saudacao = \`Olá, ${nome}! Como você está?\`;`  
O resultado seria: `"Olá, Ana! Como você está?"`

---

### 2. 🔠 Métodos em Strings
As strings em JavaScript vêm equipadas com uma variedade de métodos úteis para manipulação e consulta.

- **`.toUpperCase()` e `.toLowerCase()`**: Alteram a capitalização da string.
- **`.trim()`**: Remove espaços em branco do início e do fim da string.
- **`.includes(substring)`**: Verifica se a string contém a substring especificada.
- **`.replace(original, substituto)`**: Substitui parte da string.

---

### 3. 🔢 Métodos em Números
JavaScript oferece métodos para trabalhar com números, facilitando a realização de tarefas comuns.

- **`.toFixed(n)`**: Arredonda o número para um número específico de casas decimais.
- **`parseInt(string, base)` e `parseFloat(string)`**: Convertem strings para números inteiros e de ponto flutuante, respectivamente.

---

### 4. ➗ Métodos Matemáticos
O objeto **`Math`** fornece várias funções e constantes matemáticas.

- **`Math.round(numero)`**: Arredonda o número para o inteiro mais próximo.
- **`Math.max(...numeros)` e `Math.min(...numeros)`**: Retornam o maior e o menor valor entre os argumentos fornecidos, respectivamente.
- **`Math.random()`**: Gera um número aleatório entre 0 (inclusive) e 1 (exclusivo).

---

### 5. 🏷️ Criando Objetos e Keys com uma Variável
JavaScript permite a criação dinâmica de objetos, inclusive utilizando variáveis para definir chaves.

#### Objetos Literais
Podem ser definidos usando chaves `{}` com pares de chave-valor.

#### Chaves Dinâmicas
Quando uma chave precisa ser dinâmica ou baseada em uma variável, podemos usar a sintaxe de colchetes (`[]`).

Ex:  
`let chaveDinamica = "nome";`  
`let objeto = { [chaveDinamica]: "Ana" };`  
O resultado seria: `{ nome: "Ana" }`

---

## 📚 Considerações Importantes

- **Template literals** tornam o código mais legível e facilitam a inclusão de variáveis e expressões dentro de strings.
- Os **métodos de strings e números** são ferramentas poderosas para manipular dados e devem ser utilizados para tornar o código mais conciso e expressivo.
- O objeto **Math** e seus métodos são essenciais para realizar operações matemáticas complexas de forma simples.
- A capacidade de **criar chaves de objeto dinamicamente** aumenta a flexibilidade dos objetos em JavaScript, permitindo estruturas de dados mais dinâmicas e adaptáveis.

---

No dia 8, expandimos significativamente nossa compreensão e habilidade em trabalhar com dados e estruturas em JavaScript, explorando recursos avançados que nos permitem escrever código mais expressivo e eficaz. Continue praticando com esses conceitos e veja como eles podem ser aplicados para resolver problemas do mundo real.

Como sempre, estou à disposição para esclarecer dúvidas e explorar mais exemplos! 🚀
