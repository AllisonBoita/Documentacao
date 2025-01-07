# 📅 Resumo do Dia 5 - Arrays e Tuples

## 📚 Arrays

Em TypeScript, um array pode ser definido de várias formas. A forma mais comum é especificando o tipo de seus elementos, como por exemplo:

- Para um array de números, você pode usar o tipo `number[]`, indicando que todos os elementos do array serão números.
- Você também pode usar a notação genérica `Array<number>`, que é equivalente à forma anterior.

### Exemplos:
- `let numeros: number[] = [1, 2, 3];`
- `let numeros: Array<number> = [1, 2, 3];`

Além disso, o TypeScript permite que você defina arrays de tipos mistos, mas é importante especificar isso corretamente.

### Exemplo:
- `let misto: (string | number)[] = [1, 'dois', 3];`

---

## 🔢 Tuples

Tuples são uma estrutura semelhante a arrays, mas com a diferença de que você pode definir tipos diferentes para cada posição do array.

Em TypeScript, você pode declarar uma tuple especificando os tipos de cada elemento, ou seja, cada posição da tuple terá um tipo distinto.

### Exemplo:
- `let tupla: [string, number] = ['João', 30];`

Aqui, o primeiro elemento será do tipo `string` e o segundo do tipo `number`. Tuples também podem ser usadas com um número fixo de elementos e tipos diferentes para cada um.

---

## 🏷️ Enum

Os **Enums** em TypeScript permitem que você defina um conjunto de valores nomeados, tornando o código mais legível e expressivo. Um Enum pode ser numérico ou de string, e facilita a gestão de constantes.

### Exemplos:
- **Enum numérico**: 
  `enum Cor { Vermelho, Verde, Azul }`
  - O valor de `Vermelho` será 0, `Verde` será 1 e `Azul` será 2.
  
- **Enum de string**:
  `enum Status { Ativo = 'ATIVO', Inativo = 'INATIVO' }`
  - Neste caso, cada valor é explicitamente definido como uma string.

**Enums** ajudam a melhorar a legibilidade do código e evitam o uso de "valores mágicos" (números ou strings não identificáveis diretamente no código).

---

## 🔙 Function Return

Quando você define uma função em TypeScript, pode especificar o tipo do valor de retorno da função. Se a função não retornar nada, o tipo de retorno será `void`.

### Exemplo:
- Uma função que retorna um número pode ser definida como:
  `function somar(a: number, b: number): number { return a + b; }`

O tipo de retorno deve corresponder ao valor retornado pela função. Se a função não retornar um valor, o tipo de retorno será `void`.

---

## 🚫 Void

O tipo `void` em TypeScript é utilizado para indicar que uma função não retorna nenhum valor. Ele é frequentemente usado em funções que têm efeitos colaterais (como alterações em variáveis ou interfaces externas) e não precisam retornar nada.

### Exemplo:
`function mostrarMensagem(mensagem: string): void { console.log(mensagem); }`

No exemplo acima, a função `mostrarMensagem` não retorna nenhum valor, apenas executa uma ação (mostrar a mensagem no console).

---

✨ **Conclusão do Dia**

Em **TypeScript**, as **arrays** e **tuples** oferecem estruturas de dados flexíveis, permitindo a criação de coleções de dados com tipos fixos ou mistos. Os **Enums** tornam o código mais legível e organizam valores constantes de forma eficiente. O tipo de **retorno de funções** ajuda a garantir a consistência no que é esperado de uma função, enquanto **void** é usado para funções que não precisam retornar um valor.
