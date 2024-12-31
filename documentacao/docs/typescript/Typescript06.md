## 🏷️ Objetos

Em **TypeScript**, objetos são usados para representar coleções de dados que podem ter diferentes propriedades, com cada uma podendo ter tipos específicos. Você pode definir tipos de objetos diretamente, ou usar interfaces e tipos para estruturar esses objetos.

### Exemplo:
- Definir um tipo para um objeto com propriedades específicas:
  - `let pessoa: { nome: string, idade: number } = { nome: 'Carlos', idade: 28 };`

Outra forma de definir objetos é utilizando **interfaces**, que são úteis para descrever a estrutura de objetos complexos.

### Exemplo:
- `interface Pessoa { nome: string; idade: number; }`
- `let pessoa: Pessoa = { nome: 'Maria', idade: 32 };`

Interfaces também podem ser usadas para garantir que objetos implementem métodos ou propriedades específicas.

---

## ❓ Unknown

O tipo `unknown` é um tipo genérico que representa valores desconhecidos. Ao contrário de `any`, você não pode acessar propriedades ou chamar métodos diretamente em um valor do tipo `unknown` sem antes fazer uma verificação de tipo.

### Exemplo:
- `let valor: unknown;`
- `valor = 5;`
- Se você tentar fazer algo como `valor.toFixed()`, o **TypeScript** gerará um erro, pois o tipo é desconhecido e pode não ter o método `toFixed`.

Para usar um valor `unknown`, você deve primeiro verificar seu tipo, como com `typeof` ou `instanceof`, ou fazer uma asserção de tipo.

### Exemplo:
- `if (typeof valor === 'string') { console.log(valor.length); }`

O tipo `unknown` é útil quando você está lidando com dados de fontes externas ou quando precisa garantir que o tipo seja validado antes de ser usado.

---

## 🚫 Never

O tipo `never` é um tipo especial que representa valores que nunca ocorrem. Isso pode ser útil para funções que lançam exceções ou nunca retornam. Por exemplo, funções que terminam com um erro ou que entram em um loop infinito podem ter um tipo de retorno `never`.

### Exemplos:
- `function erro(): never { throw new Error("Erro ocorrido"); }`
- `function loopInfinito(): never { while (true) {} }`

O tipo `never` também é usado em casos de verificação de tipos em funções de análise, indicando que o código nunca deve chegar a esse ponto.

---

## 🔠 Alias

Um **alias de tipo** é uma maneira de criar um novo nome para um tipo existente. Usando a palavra-chave `type`, você pode definir um tipo que pode ser reutilizado em diferentes partes do código.

### Exemplo:
- `type ID = string | number;`
- Isso cria um alias chamado `ID`, que pode ser um `string` ou um `number`.

Aliases de tipos são úteis para simplificar tipos complexos ou frequentemente usados, tornando o código mais legível e fácil de manter.

---

## 🔗 Union

O tipo **union** permite que uma variável tenha múltiplos tipos possíveis. Isso é útil quando você deseja permitir diferentes tipos de valores para uma variável ou parâmetro de função.

### Exemplo:
- `let valor: string | number = "Texto";`
- Aqui, a variável `valor` pode ser tanto uma string quanto um número.

O **TypeScript** irá permitir que você use qualquer um dos tipos da união, mas você precisa ter cuidado ao acessar propriedades ou chamar métodos que não existam em todos os tipos possíveis na união.

---

## 🔤 Literal

Os tipos **literais** em TypeScript permitem que você defina um valor específico que uma variável pode ter. Em vez de apenas especificar o tipo (como `string`), você pode restringir o valor a um literal exato.

### Exemplo:
- `let status: "ativo" | "inativo" = "ativo";`
- Neste exemplo, a variável `status` só pode ser um dos dois valores literais: `"ativo"` ou `"inativo"`.

Os tipos literais são úteis quando você precisa restringir um valor a um conjunto bem definido de opções, como para representar estados de uma máquina ou status de processos.

---

## ➕ Intersection

O tipo **intersection** permite combinar múltiplos tipos em um único tipo. Com isso, uma variável ou objeto deve ser capaz de satisfazer todas as condições de cada tipo combinado.

### Exemplos:
- `type Pessoa = { nome: string; idade: number };`
- `type Endereco = { rua: string; cidade: string };`
- `type PessoaEndereco = Pessoa & Endereco;`

Aqui, o tipo `PessoaEndereco` é uma combinação dos tipos `Pessoa` e `Endereco`, significando que o objeto deve ter todas as propriedades de ambos.

As **interseções** são úteis quando você precisa combinar várias entidades de maneira que um objeto deva possuir as características de todas essas entidades.

---

## 📝 Conclusão

Em **TypeScript**, os conceitos de **objetos**, **unknown**, **never**, **alias**, **union**, **literal** e **intersection** são fundamentais para criar tipos que tornam o código mais robusto, legível e seguro. Utilizando essas ferramentas, você pode definir comportamentos complexos e garantir que os dados sejam manipulados corretamente, com validações de tipos avançadas.
