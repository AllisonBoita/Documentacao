# 📚 Resumo do Dia 10: Arrays em JavaScript

No décimo dia, exploramos o conceito de **Arrays** em JavaScript, uma estrutura de dados fundamental que permite armazenar múltiplos valores em uma única variável. Discutimos como acessar e modificar elementos de um **Array** para manipulação de dados. Aqui está um resumo detalhado:

---

## 1. 🧳 O que é uma Array
**Definição**: Uma **Array** em JavaScript é um objeto global usado para armazenar múltiplos valores em uma lista ordenada. Cada item na lista tem um índice, começando por 0, que pode ser usado para acessar o valor.

---

## 2. 🔍 Acessando Itens Dentro de uma Array

**Acesso por Índice**: Para acessar um elemento de uma **Array**, usa-se o índice do elemento entre colchetes.  
Ex:  
`let frutas = ["Maçã", "Banana", "Pera"];`  
`frutas[1]` retorna **"Banana"**.

**Índices Negativos**: JavaScript não suporta índices negativos diretamente, mas é possível acessar elementos do fim para o início usando a sintaxe **`array[array.length - n]`**, onde **n** é o número de itens a contar do fim.  
Ex:  
`frutas[frutas.length - 1]` retorna **"Pera"**.

---

## 3. 🔄 Modificando Elementos na Array

**Alteração Direta**: Pode-se alterar um elemento da **Array** diretamente através do seu índice.  
Ex:  
`frutas[1] = "Laranja";`  
Isso substitui **"Banana"** por **"Laranja"** na **Array frutas**.

**Adicionando Novos Elementos**: Novos elementos podem ser adicionados à **Array** ao especificar um índice que ainda não existe.  
Ex:  
`frutas[3] = "Manga";`  
Isso adiciona **"Manga"** à **Array frutas**.

---

## 📚 Considerações Importantes

- **Arrays** são estruturas de dados extremamente versáteis e são fundamentais para a manipulação de listas de dados em JavaScript.
- Aprender a manipular **Arrays** eficientemente, incluindo o acesso e modificação de elementos, bem como a utilização de seus métodos, é essencial para qualquer desenvolvedor JavaScript.
- O dia 10 foi dedicado a compreender e praticar com **Arrays**, uma das estruturas de dados mais importantes em JavaScript. Dominar **Arrays** e seus métodos é fundamental para manipular coleções de dados de maneira eficaz em seus programas.

---

Continue experimentando com esses conceitos e métodos, e não hesite em entrar em contato para explorar mais funcionalidades ou esclarecer dúvidas! 🚀
