## Nesta aula, você aprendeu:

- Implementar um FAB

O FAB é um botão bastante presente em diversos Apps para realizar as ações primárias da tela, como o cadastro de produtos.

- Adicionar ícones com o AS

Ao utilizar componentes que utilizam recursos como imagens ou ícone, podemos utilizar o AS para utilizar recursos já existentes no projeto ou adicionar novos recursos a partir do seu assistente que permite adicionar drawables, assets de imagens ou vetoriais.

- Salvar e buscar objetos por meio do DAO

Para que seja possível salvar objetos e buscá-los a partir de qualquer Activity, utilizamos o padrão de projeto DAO (Data Access Object ou Objecto de Acesso a Dados), que é uma classe responsável por abstrair a forma como os dados são salvos e recuperados pelas entidades do Android.

- O ciclo de vida de Activity

Além do ciclo de criação,as Activities do Android possuem outros ciclos que são acionados em diferentes momentos para indicar a situação atual da Activity, como o resumo que identifica que a Activity está em execução ou o pause para a Activity não está mais visível.

- Finalização do fluxo de salvar e buscar produtos

Para finalizar o fluxo de salvar e buscar produtos, notamos a necessidade de um padrão para manter os dados e o uso consciente da sobrescrita de ciclos da Activity, como o onResume() para sempre executar um código cada vez que a Activity está em execução, ou seja, é apresentada.
