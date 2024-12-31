### 🔒 Modificadores de Acesso no TypeScript

| Modificador  | Acesso                                              | Uso Principal                                     |
|--------------|-----------------------------------------------------|--------------------------------------------------|
| **`public`** | Acessível de qualquer lugar (classe, subclasse e fora). | É o padrão (não precisa declarar explicitamente). |
| **`private`** | Acessível apenas dentro da própria classe.           | Garante encapsulamento completo da propriedade/método. |
| **`protected`** | Acessível dentro da classe e de suas subclasses.    | Permite controle em hierarquias de herança.      |

---

#### 💡 Exemplos

Em **TypeScript**, podemos usar os modificadores de acesso para controlar a visibilidade de propriedades e métodos dentro das classes.

Abaixo, temos um exemplo que ilustra os três modificadores:

- **`public`**: A propriedade ou método é acessível de qualquer lugar.
- **`private`**: A propriedade ou método só pode ser acessado dentro da própria classe.
- **`protected`**: A propriedade ou método pode ser acessado dentro da classe e de suas subclasses.

```typescript
class Example {
    public publicProperty: string = "Accessible anywhere";
    private privateProperty: string = "Accessible only within this class";
    protected protectedProperty: string = "Accessible within this class and subclasses";

    public publicMethod() {
        console.log(this.publicProperty); // OK
        console.log(this.privateProperty); // OK
        console.log(this.protectedProperty); // OK
    }

    private privateMethod() {
        console.log("Private method");
    }

    protected protectedMethod() {
        console.log("Protected method");
    }
}

class SubExample extends Example {
    accessProperties() {
        console.log(this.publicProperty); // OK
        // console.log(this.privateProperty); // Erro: 'privateProperty' é privado
        console.log(this.protectedProperty); // OK
    }
}

const example = new Example();
console.log(example.publicProperty); // OK
// console.log(example.privateProperty); // Erro: 'privateProperty' é privado
// console.log(example.protectedProperty); // Erro: 'protectedProperty' é protegido
example.publicMethod(); // OK