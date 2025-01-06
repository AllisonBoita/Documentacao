# 📚 Resumo do Dia 4 - Tipos de Dados, Dados Primitivos e Dados de Referência em JavaScript

No quarto dia da nossa jornada em JavaScript, exploramos os **tipos de dados disponíveis**, diferenciando entre **dados primitivos** e **dados de referência**. Este conhecimento é essencial para manipular dados de forma eficaz em nossos programas. Vamos revisar os conceitos-chave:

---

## 🔑 **Tipos de Dados em JavaScript**

JavaScript categoriza os valores em dois grandes grupos:
1. **Dados Primitivos**
2. **Dados de Referência**

### ✨ **Dados Primitivos**
São os tipos de dados mais básicos da linguagem e têm a característica de serem **imutáveis**. Quando você manipula um valor primitivo, está **criando um novo valor**.

#### Principais tipos primitivos:
- **String**: Sequências de caracteres usadas para representar texto.  
  **Exemplo:** `"Olá, mundo!"`
- **Number**: Representa tanto números inteiros quanto números de ponto flutuante.  
  **Exemplo:** `42`, `3.14`
- **BigInt**: Para números inteiros muito grandes que o tipo `Number` não pode representar.  
  **Exemplo:** `9007199254740991n`
- **Boolean**: Representa valores lógicos: `true` ou `false`.  
  **Exemplo:** `let ativo = true;`
- **Undefined**: Indica que uma variável foi declarada, mas **ainda não recebeu valor**.
- **Null**: Representa a **ausência intencional de valor**.
- **Symbol**: Introduzido no ES6, representa valores **únicos** que não são iguais a nenhum outro valor.  
  **Exemplo:** `const id = Symbol("id");`

---

### 🏗️ **Dados de Referência (Objetos)**

Ao contrário dos tipos primitivos, os **dados de referência** são **coleções de propriedades** e **mutáveis**. Trabalhar com eles envolve manipular **referências** ao espaço na memória onde esses dados estão armazenados.

#### Principais tipos de dados de referência:
- **Objetos**: Coleções de pares **chave-valor**.  
  **Exemplo:** `{ nome: "João", idade: 30 }`
- **Arrays**: Listas ordenadas de valores.  
  **Exemplo:** `[1, 2, 3, "texto"]`
- **Funções**: Blocos de código reutilizáveis.  

**Exemplo:** 

```javascript
function cumprimentar() { 
    console.log("Olá!"); 
}
```

### 🔄 **Comportamento na Atribuição e Passagem**

- **Dados Primitivos**:  
  Ao atribuir ou passar tipos primitivos, é feita **uma cópia do valor**. Isso significa que, se você alterar o valor posteriormente, a **cópia original não será afetada**.

- **Dados de Referência**:  
  Ao atribuir ou passar objetos, arrays ou funções, você está passando **uma referência ao objeto original**. Isso significa que, se você modificar o objeto por meio de uma das referências, **todas as outras referências refletirão a mudança**.

---

### ⚠️ **Considerações Importantes**

1. **Entender a diferença entre tipos primitivos e de referência** é crucial para evitar **efeitos colaterais indesejados** em seu código, especialmente ao trabalhar com funções e métodos que alteram os dados passados.

2. Ao trabalhar com dados de referência, você pode utilizar métodos como:
   - `Object.assign()`
   - O operador de espalhamento (`...`)

   Esses métodos permitem **criar cópias de objetos**, evitando a modificação do objeto original.

---

Compreender essas diferenças é essencial para manipular dados corretamente em JavaScript e prevenir bugs. Experimente aplicar esses conceitos no código e observe como os diferentes tipos de dados se comportam. 🚀
