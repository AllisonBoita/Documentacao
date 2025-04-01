### Faça como eu fiz: Implementando o design do formulário

Vá para o arquivo de layout da FormularioProdutoActivity e implemente o design conforme a proposta de implementação:

Tela de preview do layout apresentando o formulário de produto com três campos: nome, descrição e valor do produto e um botão de salvar na parte inferior da tela

Para isso, utilize três EditText para apresentar os campos do produto. Configure os EditText para que todos fiquem alinhados verticalmente, mantendo a seguinte ordem: nome, descrição e valor.

Após adicionar cada campo, configure os EditText para apresentarem a dica do que eles representam com o android:hint, por exemplo, para o campo do nome, coloque a dica para indicar que representa o nome, e faça isso sucessivamente para os demais campos.

Lembre-se de utilizar o match constraint (0dp) para as larguras crescerem de acordo com as constraints de início e fim.

Depois de configurar os campos do produto, adicione o botão para salvar na parte inferior do layout. Para isso use o Button e adicione o texto "Salvar" para indicar a sua ação.

Por fim, rode o App e confira se apresenta o layout conforme o esperado.

Lembre-se de configurar o arquivo de manifesto do Android para rodar o formulário ao invés da lista de produtos.

### Faça como eu fiz: Refatorando o layout do formulário

Ajuste o layout do formulário de produto para manter as seguintes características:

Manter o teclado virtual de acordo com o tipo do campo.
Disponibilizar o acesso a todos os componentes visuais, mesmo que não sejam apresentados na tela ou se estiver fazendo uma edição de um campo.
Para ajustar o teclado virtual, altere o campo android:inputType de cada EditText. Para permitir o acesso a todos os campos do formulário, utilize o ScrollView como elemento raiz do layout. Em seguida, migre todos os imports de namespaces para o ScrollView.

Namespaces de layout sempre devem ser declarados no elemento raiz.

Após configurar os namespaces, coloque a altura e a largura para preencher conforme o pai (match_parent) e utilize o atributo android:fillViewport com o valor true para que o ScrollView preencha toda a tela de exibição.

Após essa modificação, faça com que a primeira View filha do ScrollView, o ConstraintLayout, cresça conforme o seu conteúdo (wrap_content).

Por fim, configure a constraint de topo do botão salvar para que fique sempre abaixo do último campo do produto, nesse caso, o campo do valor. Então, configure o vertical bias (app:layout_constraintVertical_bias) para que o botão fique sempre na extremidade de baixo das constraints do eixo Y.

Com todos os ajustes feitos, teste o App e simule os comportamentos que não deixavam o botão visível ou se o layout fica inconsistente (botão em cima do último campo) e confira se agora ele é apresentado adequadamente. Os comportamentos são:

Editar o último campo do formulário;
Último campo com uma altura que ultrapasse a tela (simulação de uma tela pequena).

### Faça como eu fiz: Adicionando ações no botão salvar

No onCreate() da FormularioProdutoActivity, busque o botão de salvar com o findViewById() e adicione um listener de clique. Dentro do listener, busque o EditText do nome do produto e faça a impressão do nome com o Log.i().

Após adicionar os ajustes, teste o App, adicione um texto no EditText para o nome, clique no botão salvar e confira se apresenta o texto esperado no logcat.

### Faça como eu fiz: Criando o produto após salvar

Dentro do listener de clique do botão de salvar, além do nome do produto, busque também a descrição e o valor fazendo o processo de binding.

Para o campo valor, verifique se ele não é vazio. Caso seja, atribua um valor padrão do tipo BigDecimal, por exemplo, o [BigDecimal.ZERO](http://bigdecimal.ZERO). Caso contrário, crie o BigDecimal a partir do valor recebido do formulário enviando como argumento do construtor.

Em seguida, crie o produto com os valores dos campos e faça a impressão do mesmo a partir do Log.i().

Para facilitar a apresentação dos valores das properties, transforme a classe Produto em uma data class.

Após todos os ajustes, teste o App, preencha os campos do formulário, clique no botão de salvar e confira se apresenta o produto com as informações esperadas no logcat.