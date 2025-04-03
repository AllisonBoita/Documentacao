## Acessando o formulário

Modifique o layout da lista de produtos e adicione o FloatingActionButton. Para isso, vá na aba de design, procure ou filtre por FloatingActionButton, segure e arraste até a tela do layout.

Ao fazer essa ação, o AS deve apresentar a tela para escolher o recurso para representar o ícone do FAB (FloatingActionButton).

Na tela para escolher o recurso, clique na cruz superior à esquerda para apresentar outras opções de recursos e, entre elas, utilize o Vector Asset, que é a opção que cria uma imagem capaz de se adaptar a diferentes tamanhos de tela.

Em seguida, mantenha a opção Clip Art selecionada no campo Asset Type, então, clique no botão para escolher o ícone no campo Clip Art.

Ao abrir uma janela nova com vários ícones, filtre por add e escolha o ícone da cruz. Nomeie o ícone. Você pode colocar, por exemplo, ic_action_add ou o nome que preferir. Clique em Next e depois Finish.

Então, selecione o ícone adicionado para o FAB. Em seguida, posicione o FAB na parte inferior à direita da tela configurando as constraints de fim e baixo.

Após configurar o FAB no layout, na MainActivity, faça o binding para pegar o FAB e configure o listener de clique para abrir a Activity de formulário ao clicar no FAB. Para isso, crie uma instância de Intent(), envie a MainActivity como Context e a classe FormularioProdutoActivity como referência, e então chame o método startActivity().

Teste o App e confira se ao clicar no FAB apresenta o formulário da Activity.

## Salvando produtos

Configure o código da FormularioProdutoActivity para salvar produtos ao clicar no botão Salvar.

Para isso, implemente o DAO para produto, criando a classe ProdutoDao e adicionando os comportamentos para salvar e buscar todos os produtos.

```kotlin
class ProdutoDao {

    companion object {
        private val produtos = mutableListOf<Produto>()
    }

    fun adiciona(produto: Produto) {
        produtos.add(produto)
    }

    fun buscaTodos(): List<Produto> {
        return produtos.toList()
    }
}
```


Então, utilize uma lista como estrutura de dados para salvar os produtos, depois de adicionar os métodos e implementá-los com base na lista interna.

Vá ao código de listener de clique do botão salvar e crie uma instância do DAO. Salve o produto criado, busque os produtos e, então, confira se ele é apresentado via log.

Por fim, ajuste o código da MainActivity para que o RecyclerView apresente a lista de produtos a partir dos produtos do DAO.

Para esta atividade, apenas confira se o produto que foi enviado para o DAO é apresentado no log que busca a lista de produtos. Como a implementação atual não deve apresentar os produtos na lista de produtos, portanto, não precisa validar esse comportamento.

## Carregando os produtos do DAO no RecyclerView

Ajuste o código para que o App consiga apresentar os produtos do DAO no RecyclerView. Para isso, primeiro finalize a Activity de formulário de produto, após salvar o produto no DAO chamando o método finish().



Em seguida, modifique o DAO para que salve os produtos em um lista via Companion Object para manter as informações disponíveis independente da instância.

Por fim, sobrescreva o método onResume() da MainActivity e migre todo o código de binding e configuração do RecyclerView. Então, teste o App e confira se, ao salvar um produto pelo formulário, o App volta para a lista de produtos e apresenta o produto salvo. Faça esse mesmo teste mais de uma vez para garantir que tudo está funcionando como esperado.

```kotlin
override fun onResume() {
    super.onResume()

    val recyclerView = findViewById<RecyclerView>(R.id.recyclerView)
    val dao = ProdutoDao()
    val produtos = dao.buscaTodos()

    recyclerView.adapter = ListaProdutosAdapter(produtos)
}
```

No ListaProdutosAdapter.kt, certifique-se de que os produtos são exibidos corretamente:

```kotlin
class ListaProdutosAdapter(private val produtos: List<Produto>) :
    RecyclerView.Adapter<ListaProdutosAdapter.ViewHolder>() {

    class ViewHolder(view: View) : RecyclerView.ViewHolder(view) {
        fun vincula(produto: Produto) {
            val nome = itemView.findViewById<TextView>(R.id.item_nome)
            val descricao = itemView.findViewById<TextView>(R.id.item_descricao)
            val preco = itemView.findViewById<TextView>(R.id.item_preco)

            nome.text = produto.nome
            descricao.text = produto.descricao
            preco.text = produto.preco.toPlainString()
        }
    }

    override fun onCreateViewHolder(parent: ViewGroup, viewType: Int): ViewHolder {
        val view = LayoutInflater.from(parent.context)
            .inflate(R.layout.item_produto, parent, false)
        return ViewHolder(view)
    }

    override fun onBindViewHolder(holder: ViewHolder, position: Int) {
        val produto = produtos[position]
        holder.vincula(produto)
    }

    override fun getItemCount(): Int = produtos.size
}
```
