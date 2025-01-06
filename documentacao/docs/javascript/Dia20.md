Resumo da Aula: Dia 19 - Funções, Parâmetros Padrão e Rest em JavaScript


O que são Funções?
As funções são um dos blocos de construção fundamentais em JavaScript, permitindo agrupar uma série de instruções para realizar uma tarefa específica. Elas podem ser chamadas a qualquer momento, permitindo a reutilização de código e a criação de códigos mais modulares e legíveis.



Parâmetros Padrão
Os parâmetros padrão (default parameters) permitem definir valores iniciais para os parâmetros de uma função. Essa funcionalidade é útil para garantir que a função tenha um comportamento adequado mesmo quando não receba todos os argumentos esperados. Exemplo:



function saudar(nome = "visitante") {
  console.log(`Olá, ${nome}!`);
}


Nesse caso, se a função saudar for chamada sem argumentos, ela usará "visitante" como o nome padrão.



Parâmetros Rest
Os parâmetros rest permitem que uma função aceite um número indefinido de argumentos como um array, proporcionando uma grande flexibilidade. Eles são indicados pelo prefixo ... antes do nome do parâmetro. Isso é especialmente útil para funções que precisam lidar com múltiplos argumentos sem saber antecipadamente quantos serão. Exemplo:



function somar(...numeros) {
  return numeros.reduce((total, atual) => total + atual, 0);
}


A função somar pode receber qualquer número de argumentos e retorna a soma de todos eles.



Conclusão
Entender funções, parâmetros padrão e rest é fundamental para aproveitar todo o potencial do JavaScript na criação de códigos flexíveis, reutilizáveis e eficientes. As funções ajudam a organizar o código e os parâmetros padrão/rest ampliam enormemente a adaptabilidade das funções a diferentes situações de uso.