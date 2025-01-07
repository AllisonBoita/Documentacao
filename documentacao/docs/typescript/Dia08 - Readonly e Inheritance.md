# 📅 Resumo do Dia 8 - Readonly e Inheritance

O modificador `readonly` em TypeScript torna uma propriedade somente leitura, ou seja, uma vez definida, não pode ser alterada. Isso é útil quando você quer garantir que o valor de uma propriedade não seja modificado após a criação do objeto.

Exemplo:

```typescript
class Person {
    readonly name: string;

    constructor(name: string) {
        this.name = name;
    }

    changeName(newName: string) {
        // this.name = newName; // Erro: A propriedade 'name' é somente leitura.
    }
}
```

---

## Parâmetro do Constructor

Em TypeScript, é possível declarar propriedades diretamente no construtor, tornando o código mais conciso. Isso elimina a necessidade de declarar explicitamente as propriedades da classe antes de inicializá-las no construtor. O TypeScript automaticamente cria as propriedades com os valores passados no momento da criação do objeto.

```typescript
class Car {
    constructor(public make: string, public model: string, private year: number) {}

    getCarInfo() {
        return `${this.year} ${this.make} ${this.model}`;
    }
}

const myCar = new Car('Toyota', 'Corolla', 2021);
console.log(myCar.getCarInfo()); // 2021 Toyota Corolla
```

---

## Index Signatures

As **index signatures** permitem que você defina propriedades com chaves dinâmicas em um objeto. Isso é útil quando você não sabe os nomes exatos das propriedades em tempo de compilação, mas deseja garantir que todos os valores atendam a um tipo específico.

```typescript
interface Dictionary {
    [key: string]: string;
}

const myDictionary: Dictionary = {
    hello: 'world',
    bye: 'farewell'
};

console.log(myDictionary.hello); // world
```

---

## Inheritance (Herança)

A **herança** permite que uma classe derive de outra, herdando suas propriedades e métodos. Isso promove o reuso de código e facilita a manutenção.

```typescript
class Animal {
    constructor(public name: string) {}

    speak() {
        console.log(`${this.name} makes a noise.`);
    }
}

class Dog extends Animal {
    constructor(name: string) {
        super(name);
    }

    speak() {
        console.log(`${this.name} barks.`);
    }
}

const dog = new Dog('Rex');
dog.speak(); // Rex barks.

```

---

## Overriding (Sobrescrita)

A **sobrescrita** ocorre quando uma classe filha redefine um método de sua classe mãe. A ideia por trás disso é fornecer uma implementação mais específica de um método que foi definido em uma classe base.

```typescript
class Shape {
    area(): number {
        return 0;
    }
}

class Circle extends Shape {
    constructor(public radius: number) {
        super();
    }

    area(): number {
        return Math.PI * this.radius * this.radius;
    }
}

const circle = new Circle(5);
console.log(circle.area()); // 78.53981633974483
```