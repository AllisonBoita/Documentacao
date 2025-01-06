Resumo do dia 13
No dia 13, mergulhamos no conceito fundamental de controle de fluxo em JavaScript através do uso de estruturas condicionais if, else if e else. Essas estruturas nos permitem tomar decisões no código baseando-nos em condições específicas, levando a diferentes resultados de acordo com os dados que temos.

Conceitos Chave Abordados:
Estrutura if: Usada para testar uma condição inicial. Se a condição for verdadeira (true), o bloco de código dentro do if será executado.

Estrutura else: Anexada a um if, a cláusula else captura qualquer situação que não atenda à condição do if. Seu bloco de código é executado se a condição testada pelo if for falsa (false).

Estrutura else if: Usada para testar múltiplas condições em sequência. Se a condição do if inicial for falsa, o else if oferece uma nova condição a ser testada antes de possivelmente recorrer ao else.

Exemplo Prático:
O desafio proposto ilustra perfeitamente como usar essas estruturas para criar um sistema de avaliação baseado em pontuação:

let grade = 92;

if (grade >= 90) {
console.log('Excelente!');
} else if (grade >= 75) {
console.log('Muito Bom!');
} else {
console.log('Você pode melhorar :)');
}

Neste exemplo, a pontuação (grade) é avaliada da seguinte forma:

if (grade >= 90): Verifica se a pontuação é 90 ou superior. Se for, "Excelente!" é impresso no console.

else if (grade >= 75): Se a pontuação não for 90 ou mais (o que faz a condição do if anterior ser falsa), essa nova condição verifica se a pontuação é pelo menos 75. Se for, "Muito Bom!" é impresso.

else: Se nenhuma das condições anteriores for verdadeira (a pontuação é menor que 75), "Você pode melhorar :)" é impresso.

Importância:
Essa abordagem demonstra como podemos direcionar o fluxo do programa baseando-nos em condições e valores variáveis, o que é uma habilidade essencial no desenvolvimento de software. Entender e aplicar corretamente as estruturas condicionais permite a criação de programas dinâmicos e interativos que respondem de maneira diferente a diferentes entradas e situações.
