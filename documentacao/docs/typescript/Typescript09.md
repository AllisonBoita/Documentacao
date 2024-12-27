## Tipos Literais

Os **tipos literais** permitem que você defina um valor específico para uma variável, ao invés de apenas um tipo genérico como `string` ou `number`. Isso é útil quando você quer restringir um valor a um conjunto específico de opções.

Exemplo:

```typescript
let status: "ativo" | "inativo" = "ativo";
status = "inativo"; // Válido
status = "pendente"; // Erro: o valor 'pendente' não é do tipo 'ativo' ou 'inativo'
```

## Tipo any

O tipo any é um tipo especial que permite que uma variável tenha qualquer valor. O TypeScript não realiza nenhuma verificação de tipo em variáveis do tipo any, o que pode ser útil em algumas situações, mas também pode causar problemas se não for usado com cautela.

Exemplo:

```typescript
let valor: any = 5;
valor = "Texto"; // Válido
valor = true; // Válido
```

Uso com cuidado
Embora any seja flexível, é recomendado usar tipos mais específicos sempre que possível, para evitar problemas de tipo no futuro.

## Tipos Genéricos

Tipos genéricos permitem criar funções, classes ou interfaces que podem trabalhar com qualquer tipo de dado. Eles proporcionam flexibilidade, mantendo a segurança de tipo.

Exemplo:

```typescript
function identidade<T>(valor: T): T {
  return valor;
}

let numero = identidade(5); // Tipo inferido como 'number'
let texto = identidade("Olá"); // Tipo inferido como 'string'
```

Aqui, T é um tipo genérico que será substituído pelo tipo do valor que for passado para a função.

## Union Types (Tipos União)

Union types permitem que uma variável tenha mais de um tipo. Isso significa que a variável pode ser de diferentes tipos, mas você pode realizar verificações para garantir que o tipo seja tratado corretamente.

Exemplo:

```typescript

let identificador: string | number;

identificador = "123"; // Válido
identificador = 123;   // Válido
identificador = true;  // Erro: 'boolean' não é atribuível ao tipo 'string | number'
```

## Intersection Types (Tipos de Interseção)

Intersection types permitem combinar vários tipos em um único tipo. O valor de uma variável com tipos de interseção deve ser compatível com todos os tipos combinados.

Exemplo:

```typescript
interface Pessoa {
  nome: string;
  idade: number;
}

interface Empregado {
  cargo: string;
  salario: number;
}

type PessoaEmpregada = Pessoa & Empregado;

const trabalhador: PessoaEmpregada = {
  nome: "Carlos",
  idade: 30,
  cargo: "Desenvolvedor",
  salario: 5000
};
```

Aqui, PessoaEmpregada é uma interseção de Pessoa e Empregado, o que significa que a variável deve conter todas as propriedades de ambos.

## Tipo unknown

O tipo unknown é similar ao tipo any, mas com uma diferença importante: você precisa fazer uma verificação de tipo antes de manipular um valor do tipo unknown, o que torna o código mais seguro.

Exemplo:

```typescript
let valor: unknown = 10;

if (typeof valor === "number") {
  console.log(valor.toFixed(2)); // Válido
}
```

Se você tentar acessar propriedades ou chamar métodos em um valor do tipo unknown sem verificar o tipo, o TypeScript emitirá um erro.

## Null e Undefined

Null e undefined são tipos que representam valores "ausentes" ou "não atribuídos". O TypeScript os trata como tipos distintos, mas você pode configurar se deseja ou não permitir esses valores em seu código.

null: Representa a ausência intencional de um valor.
undefined: Representa uma variável que foi declarada, mas não foi atribuída a nenhum valor.

Exemplo:

```typescript
let valor: null = null; // Válido
let outroValor: undefined = undefined; // Válido

let naoDefinido: string | undefined;
naoDefinido = undefined; // Válido
```

## Tipos de Funções

Funções no TypeScript podem ser tipadas para garantir que os parâmetros e o valor de retorno estejam de acordo com o tipo esperado.

Exemplo de tipo de função:
```typescript
function add(x: number, y: number): number {
  return x + y;
}
```

## Tuplas
Tuplas são tipos especiais de arrays que permitem que você defina um conjunto fixo de elementos, cada um com um tipo diferente. O TypeScript irá garantir que a tupla siga a estrutura definida.

Exemplo de tupla:

```typescript
let person: [string, number] = ["Alice", 25];
person = ["Bob", 30]; // válido
person = [25, "Alice"]; // erro
```

## Enums
Os enums permitem que você defina um conjunto nomeado de valores, o que pode ser útil para representar estados ou categorias.

Exemplo de enum:
```typescript
enum Direction {
  Up = "UP",
  Down = "DOWN",
  Left = "LEFT",
  Right = "RIGHT"
}

let direction: Direction = Direction.Up;
```

## Tipo never
O tipo never é usado para representar valores que nunca acontecem, como funções que lançam exceções ou que têm loops infinitos.

Exemplo de tipo never:
```typescript
function throwError(message: string): never {
  throw new Error(message);
}
```

## Definição de Objetos
Em TypeScript, você pode definir tipos para objetos, permitindo que você defina as propriedades e os tipos associados a elas.

Exemplo de definição de objeto:
```typescript
interface Person {
  name: string;
  age: number;
}

const person: Person = {
  name: "John",
  age: 30
};
```

## Classes
As classes em TypeScript permitem a definição de objetos com propriedades e métodos. As classes são fundamentais para a programação orientada a objetos (OOP).

Exemplo de classe:
```typescript
class Car {
  brand: string;
  model: string;
  year: number;

  constructor(brand: string, model: string, year: number) {
    this.brand = brand;
    this.model = model;
    this.year = year;
  }

  displayInfo() {
    console.log(`${this.brand} ${this.model} (${this.year})`);
  }
}

const myCar = new Car("Toyota", "Corolla", 2020);
myCar.displayInfo();
```

## Herança
A herança permite que uma classe herde propriedades e métodos de outra classe. Isso facilita o código reutilizável e a organização.

Exemplo de herança:
```typescript
class Animal {
  name: string;
  
  constructor(name: string) {
    this.name = name;
  }

  speak() {
    console.log(`${this.name} makes a sound`);
  }
}

class Dog extends Animal {
  constructor(name: string) {
    super(name);
  }

  speak() {
    console.log(`${this.name} barks`);
  }
}

const dog = new Dog("Rex");
dog.speak();
```


## Overriding (Sobrescrita de Métodos)
A sobrescrita de métodos ocorre quando uma classe filha redefine um método da classe pai.

Exemplo de overriding:
```typescript
class Animal {
  speak() {
    console.log("Animal makes a sound");
  }
}

class Dog extends Animal {
  speak() {
    console.log("Dog barks");
  }
}

const myDog = new Dog();
myDog.speak(); // Dog barks
```