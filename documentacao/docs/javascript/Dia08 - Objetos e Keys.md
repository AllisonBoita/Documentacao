### 5. 🏷️ Criando Objetos e Keys com uma Variável
JavaScript permite a criação dinâmica de objetos, inclusive utilizando variáveis para definir chaves.

#### Objetos Literais
Podem ser definidos usando chaves `{}` com pares de chave-valor.

#### Chaves Dinâmicas
Quando uma chave precisa ser dinâmica ou baseada em uma variável, podemos usar a sintaxe de colchetes (`[]`).

Ex:  
`let chaveDinamica = "nome";`  
`let objeto = { [chaveDinamica]: "Ana" };`  
O resultado seria: `{ nome: "Ana" }`