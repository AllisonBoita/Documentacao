## 🔢 2. Conversão de String para Número

JavaScript permite a conversão de strings para números, seja para operações matemáticas ou validações. Aqui estão os métodos mais comuns:

### 🔍 **Métodos de Conversão**
1. **`parseInt(string):`** Converte uma string para um número inteiro.
2. **`parseFloat(string):`** Converte uma string para um número com ponto flutuante (decimais).
3. **Operador Unário `+`:** Simples e rápido para converter strings para números.
4. **`Number(string):`** Outra forma de conversão explícita.

### ⚠️ **Cuidado com Valores Inválidos**
Valores como `"abc"` ou strings vazias retornam `NaN` (Not a Number), indicando falha na conversão.

---

## ✍️ 3. Conversão de Número para String

Às vezes, é necessário converter números para strings, como em concatenações ou exibições. JavaScript oferece métodos simples para isso:

### 🔍 **Métodos de Conversão**
1. **`toString():`** Converte um número para string.
2. **Template Literals:** Uma forma moderna e flexível de conversão.
3. **`String():`** Converte explicitamente para string.

---

## 🔄 4. Conversão para Boolean

### ✅ **Valores Truthy e Falsy**
- **Falsy (convertidos para `false`):**  
  `0`, `NaN`, `null`, `undefined`, `""` (string vazia).  
- **Truthy (convertidos para `true`):**  
  Qualquer outro valor.

### 🔍 **Métodos de Conversão**
1. **Operador `Boolean():`** Converte explicitamente um valor para booleano.
2. **Double Bang `!!`:** Atalho prático para conversão.

---

## 📚 Considerações Importantes

- **Atenção aos Detalhes:** A tipagem dinâmica de JavaScript é poderosa, mas exige cuidado para evitar comportamentos inesperados.
- **Boas Práticas:**
  - Sempre valide as entradas antes de realizar conversões.
  - Prefira métodos explícitos (`Boolean()`, `Number()`) para maior legibilidade.
- **Dica:** Experimente diferentes valores e métodos para entender como funcionam na prática. 💡

---

🎉 **Resumo do Dia:**  
Hoje aprendemos sobre a flexibilidade e os desafios da tipagem dinâmica em JavaScript, explorando conversões entre **strings**, **números** e **booleanos**. Essas habilidades são essenciais para manipulação de dados e criação de lógicas eficazes.