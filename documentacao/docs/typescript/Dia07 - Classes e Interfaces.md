## 🌐 Definição de OOP

**Object Oriented Programming (OOP)**

OOP é um estilo de programação. Trabalhar com **OOP** é montar os pilares para um bom ambiente de programação.

![diagrama](./img/diagrama.png)

---

### 🏗️ Criando Classes

Classes são como fábricas onde os objetos são montados. Por exemplo, criamos os objetos utilizando os componentes (métodos e propriedades) que estão nas classes.

---

## 🛠️ Criando um Objeto com Método

Os métodos determinam o que pode acontecer com um cálculo ou o que pode ser feito com uma classe.

---

## 🔒 Organizando Código - Tornando Propriedades Públicas ou Privadas

Inicialmente, todas as propriedades são públicas, mas posso alterá-las para determinar onde serão usadas e/ou alteradas.

Exemplo:

```typescript
// Criando properties

class Users {
    name: string
    age: number
    balance: number

    // Criando método
    addMoney(amount: number){
        this.balance += amount
    }
}

const imprimirUsuario = new Users ('Allison', 25, 10)
imprimirUsuario.balance = 400
// Associando método ao usuário
imprimirUsuario.addMoney(20)
```

No código acima, é possível alterar a propriedade balance em qualquer trecho.

Alterando a propriedade para private balance: number, ela só poderá ser alterada dentro da classe.

### Criando interfaces

Interfaces foram criadas para dar estrutura à um objeto.