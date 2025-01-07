# 📅 Resumo do Dia 3 - Tipos no Typescript

O **TypeScript** introduz **tipagem estática** ao JavaScript, permitindo que você defina tipos para variáveis, funções e objetos, o que pode ajudar a evitar muitos erros comuns. Ele oferece uma vasta gama de tipos predefinidos, bem como a possibilidade de criar tipos personalizados.

---

## 🔸 Tipos Primitivos

Os tipos primitivos em **TypeScript** incluem os seguintes:

- **`string`**: Representa uma sequência de caracteres. Exemplo: `let nome: string = "João"`.
- **`number`**: Representa um número, podendo ser inteiro ou flutuante. Exemplo: `let idade: number = 30`.
- **`boolean`**: Representa um valor lógico, `true` ou `false`. Exemplo: `let ativo: boolean = true`.
- **`null`** e **`undefined`**: Representam valores nulos ou indefinidos. Exemplo: `let valorNulo: null = null` e `let valorIndefinido: undefined = undefined`.

---

## 🔸 Tipos de Objetos

Em **TypeScript**, você pode definir tipos para objetos com propriedades específicas.

- **`object`**: Define um objeto genérico. Exemplo: `let pessoa: object = { nome: "Maria", idade: 25 }`.
- **Interface**: Usada para definir tipos complexos para objetos, especificando suas propriedades e métodos. Exemplo: `interface Pessoa { nome: string; idade: number }`.

---

## 🔸 Tipos Avançados

**TypeScript** também oferece tipos mais avançados, como:

- **Union Types**: Permite que uma variável tenha mais de um tipo. Exemplo: `let identificacao: string | number = "12345"`.
- **Intersection Types**: Permite combinar múltiplos tipos em um único tipo. Exemplo: `type PessoaEndereco = Pessoa & Endereco`.
- **Generics**: Permite criar tipos que funcionam com vários tipos de dados diferentes, garantindo tipagem segura em coleções e outras estruturas de dados. Exemplo: `function identidade<T>(arg: T): T { return arg; }`.

---

✨ **Conclusão do Dia**

O sistema de tipos do **TypeScript** é uma poderosa ferramenta para melhorar a qualidade e a manutenção do código, ajudando a detectar erros antes da execução. Além dos tipos primitivos, o **TypeScript** oferece recursos como interfaces, tipos avançados e generics, permitindo uma grande flexibilidade na criação de tipos para os dados.