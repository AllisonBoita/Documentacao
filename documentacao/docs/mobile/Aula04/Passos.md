### Vinculando código com as Views

Vincule as Views do layout activity_main com a MainActivity. Para isso, dentro do onCreate(), utilize o método findViewById() enviando o TextView como generics e o id da View que deseja via argumento.

Para acessar o id da View, utilize o id da classe R.

Então, atribua para uma variável e modifique o valor do TextView de acordo com o campo do produto. Faça esse procedimento para os 3 campos que representam o produto:

nome
descrição
valor
Após fazer o processo de binding (vinculação), teste o App e confira se apresenta o resultado esperado. Fique à vontade para colocar os valores que preferir.

Após finalizar, lembre-se de ajustar os atributos android:text dos TextView para utilizar o namespace tools.

### Implementando o RecyclerView no layout

Modifique o layout para utilizar o RecyclerView. Para isso, crie um novo layout com o elemento raiz sendo o ConstraintLayout e mova todo o código que representa um produto pra ele.

Em seguida, na paleta de componentes, procure o RecyclerView, clique, pressione e arraste para a tela. Ao concluir essa ação, o Android Studio deve apresentar o preview do RecyclerView similar a este:

Animação acessando a aba Design, buscando a o RecyclerView na paleta, clicando, segurando e arrastando o RecyclerView para dentro do preview. Apresentando o preview padrão do RecyclerView com itens de 0 a 9.

Lembre-se de aplicar as constraints em todos os eixos e adicionar o android:id para o RecyclerView.

Ao adicionar o RecyclerView no layout, acesse o RecyclerView via XML e adicione o layout do produto no atributo tools:listitem para apresentar os produtos no preview do RecyclerView. Se não aparecer vários produtos no preview, ajuste o layout de produto para que a altura (android:layout_height) cresça com base no conteúdo (wrap_content).

Agora que os layouts estão separados, aproveite para utilizar o match constraint (0dp) no atributo android:layout_width em ambos os layouts. Para que isso seja possível, é importante que as constraints de eixo X (start e end) estejam configuradas.

Nesta atividade, não é necessário testar o App, pois a configuração do RecyclerView não foi concluída ainda. Sendo assim, apenas comente ou remova o código que faz o binding de Views na Activity e certifique que todos os passos da atividade foram concluídos.

### Criando o adapter da lista de produtos

Agora que o layout tem um RecyclerView acessível, no onCreate() da MainActivity, busque o RecyclerView e atribua para uma variável. Então, chame a property adapter e faça a inicialização dela a partir da referência ListaProdutosAdapter.

A classe ListaProdutosAdapter não existe, portanto, utilize o atalho Alt + Enter do Android Studio, escolha a opção Create class 'ListaProdutosAdapter' e indique que a classe será criada no pacote br.com.alura.orgs.ui.recyclerview.adapter.

Ao finalizar esta ação, o AS (Android Studio) deve criar a classe herdando de RecyclerView.Adapter<RecyclerView.ViewHolder>(). Com a classe criada, faça os imports necessários e peça para o AS implementar os seguintes métodos obrigatórios:

override fun onCreateViewHolder(
    parent: ViewGroup, 
    viewType: Int): RecyclerView.ViewHolder {
        TODO("Not yet implemented")
}

override fun onBindViewHolder(
    holder: RecyclerView.ViewHolder, 
    position: Int) {
        TODO("Not yet implemented")
}

override fun getItemCount(): Int {
      TODO("Not yet implemented")
}

Aproveite esse momento para migrar o pacote da MainActivity para que fique em br.com.alura.orgs.ui.activity. Com essa mudança, ajuste o AndroidManifest.xml para adicionar a nova localização da MainActivity.

Em seguida, receba uma lista de produtos no construtor primário da ListaProdutosAdapter para que seja possível implementar os métodos getItemCount() e o onBindViewHolder(). Aproveite para criar a classe Produto. Ela deve ter as seguintes properties:

nome: String
descricao: String
valor: BigDecimal
Por fim, implemente o getItemCount() e retorne a property size da lista de produtos. O objetivo desta atividade é inicializar a implementação do adapter do RecyclerView, portanto, não é necessário executar o App.

### Implementando os métodos do Adapter

Continuando com a implementação do Adapter, é necessário implementar os seguintes métodos:

onCreateViewHolder
onBindViewHolder
Ambos precisam do RecyclerView.ViewHolder, ou seja, antes de começar a implementação crie a classe ViewHolder dentro do adapter que herda de RecyclerView.ViewHolder.

A herança de RecyclerView.ViewHolder exige o envio de uma View em seu construtor, portanto, receba uma View no construtor primário da ViewHolder e envie para a RecyclerView.ViewHolder.

Com o ViewHolder criado, modifique o generics do adapter para utilizar o ViewHolder e modifique os métodos onCreateViewHolder() e onBindViewHolder() para utilizarem o ViewHolder em suas implementações.

Após essa modificação, no onCreateViewHolder() crie uma instância do LayoutInflater() a partir do método estático from() que recebe um Context via argumento. Adapter não tem uma referência de Context, ou seja, receba a referência de Context via construtor primário do Adapter.

Com o LayoutInflater disponível, chame o método inflate() para inflar a View e envie os seguintes argumentos:

Layout do produto: arquivo produto_item;
RecyclerView como parent: ViewGroup como parâmetro do onCreateViewHolder();
Não anexar View com o root: valor false.
Então, devolva o retorno do inflate() para uma variável que representa a View e faça uma instância do ViewHolder enviando a View como argumento do construtor. Por fim, retorne o ViewHolder para o onCreateViewHolder.

Após finalizar a implementação do onCreateViewHolder(), implemente o onBindViewHolder(). Para fazer isso, pegue o produto da lista de produtos a partir da posição, então, a partir do ViewHolder recebido via parâmetro, chame o método vincula() enviando o produto.

O método do ViewHolder ainda não existe, portanto, peça para o AS criar o método vincula() com o atalho Alt + Enter > create member function 'ListaProdutosAdapter.ViewHolder.vincula'. Ao escolher essa opção, o AS vai criar o vincula() dentro do ViewHolder recebendo o produto como parâmetro.

Então, dentro do método vincula(), faça o processo de binding de view buscando as views a partir da property itemView do RecyclerView.Adapter. No processo de binding, preencha todas as Views com as informações do produto, por exemplo, preencha a View do nome com a property nome do produto e faça o mesmo procedimento para as demais Views.

Após esta etapa, o Adapter está implementado, mas, para testar o App, envie um Context e uma lista de produtos para o ListaProdutosAdapter() dentro do onCreate() da MainActivity.

Então, configure o LayoutManager para o RecyclerView, você pode fazer a configuração dentro do código Kotlin a partir da property layoutManager ou por meio do layout a partir do atributo app:layoutManager. Entre as possibilidades, utilize o LinearLayoutManager.

Por fim, teste o App e confira se apresenta a lista de produtos conforme os produtos enviados para o adapter.