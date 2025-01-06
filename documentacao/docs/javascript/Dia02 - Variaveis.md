# 📅 Resumo do Dia 2 - Variáveis

- **O que são:** As **variáveis** são contêineres que armazenam valores de dados. Elas permitem etiquetar dados com nomes descritivos, facilitando sua referência e manipulação no código.

### 📝 **Como declarar variáveis:**

1. **`var`**: A forma mais antiga de declarar variáveis. Tem **escopo de função** e pode ser **redeclara** e **atualizada**.
   
2. **`let`**: Introduzido no **ES6 (ECMAScript 2015)**, permite declarar variáveis com **escopo de bloco**, ou seja, a variável existe apenas dentro do bloco onde foi declarada. Pode ser **atualizada**, mas **não redeclarada** no mesmo escopo.

   **Exemplo:** `let mensagem = "Olá, mundo!";`

---

## 🔧 **Manipulação de Variáveis**

- **Operações**: Uma vez declaradas, as variáveis podem ser **manipuladas** e ter seus valores **atualizados**. É possível realizar operações **matemáticas** com variáveis numéricas, **concatenar strings** e outras manipulações.

---

## 🏷️ **Constantes**

- **O que são:** As **constantes** são semelhantes às variáveis, mas uma vez que um valor é atribuído a elas, ele **não pode ser alterado**. São úteis para valores fixos que não precisam ser modificados ao longo do programa.

### 📝 **Como declarar constantes:**

- **`const`**: A palavra-chave **`const`** é usada para declarar constantes. Assim como **`let`**, ela tem **escopo de bloco** e não pode ser **redeclara** ou **atualizada**.

   **Exemplo:** `const PI = 3.14;`

---

## 🛠️ **Boas Práticas**

- **Preferir `let` e `const`** em vez de **`var`** para declarar variáveis, devido ao escopo de bloco mais previsível e à prevenção de **redeclarações acidentais**.
  
- **Usar `const`** para valores que sabemos que **não mudarão**, como **URLs de API**, **valores de configuração**, etc., para garantir a **imutabilidade** desses valores no código.


