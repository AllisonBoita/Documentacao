### Buscando as views do layout na activity

Sempre trabalharemos com tools para ver o texto no preview.

Para isso realizamos a bind entre a view e o layout.

### Introdução ao RecyclerView

O recyclerView facilita a exibição de grandes conjuntos de dados. Entrega a performance independente da quantidade de itens.

### Sobre

os conceitos de Adapter, View e Model seguem o padrão MVVM (Model-View-ViewModel) ou MVC (Model-View-Controller). Vou explicar cada um com base no seu código:

#### Model (Modelo)

O Model representa os dados da aplicação. Ele geralmente contém apenas propriedades e, em alguns casos, lógica de negócios básica. No seu caso, a classe Produto representa um Model.

📌 Exemplo no seu código:

```xml
class Produto (
    val nome: String,
    val descricao: String,
    val valor: BigDecimal,
    val disponivel: String
)
```

Produto é um modelo de dados que contém os atributos nome, descricao, valor e disponivel.

Ele não contém lógica de exibição (UI) nem controle da interface, apenas dados.

#### View (Visão)

A View é responsável por mostrar os dados ao usuário e interagir com ele. Normalmente, no Android, as Views são os layouts XML e componentes como RecyclerView, TextView, Button, etc.

📌 Exemplo no seu código:

O layout XML (activity_main.xml e product_item.xml) e a RecyclerView na MainActivity fazem parte da View.

No código da MainActivity:

```xml
val recyclerView = findViewById<RecyclerView>(R.id.recyclerView)
recyclerView.adapter = ListaProdutosAdapter(context = this, produtos = listOf( /* Lista de Produtos */ ))
```

RecyclerView é a View que exibe os produtos na tela.

A ListaProdutosAdapter vai preencher essa View com os dados dos produtos.

No layout XML (exemplo product_item.xml):

```xml
<TextView
    android:id="@+id/nome"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:text="Nome do Produto"/>
```

Esse TextView faz parte da View e será preenchido com o nome do produto pelo Adapter.

####  Adapter (Adaptador)

O Adapter atua como um "ponte" entre os dados (Model) e a interface (View). Ele pega os dados da lista e os vincula aos elementos visuais (TextView, RecyclerView, etc.).

📌 Exemplo no seu código:

A classe ListaProdutosAdapter:

```xml
class ListaProdutosAdapter (
    private val context: Context,
    private val produtos: List<Produto>
) : RecyclerView.Adapter<ListaProdutosAdapter.ViewHolder>() {

    class ViewHolder(view: View) : RecyclerView.ViewHolder(view) {
        fun vincula(produto: Produto) {
            val nome = itemView.findViewById<TextView>(R.id.nome)
            nome.text = produto.nome
        }
    }

    override fun onCreateViewHolder(parent: ViewGroup, viewType: Int): ViewHolder {
        val inflater = LayoutInflater.from(context)
        val view = inflater.inflate(R.layout.product_item, parent, false)
        return ViewHolder(view)
    }

    override fun getItemCount(): Int = produtos.size

    override fun onBindViewHolder(holder: ViewHolder, position: Int) {
        val produto = produtos[position]
        holder.vincula(produto)
    }
}
```

O Adapter recebe uma lista de Produto e os exibe na RecyclerView.

O ViewHolder mantém referência aos elementos visuais (TextView do layout product_item.xml).

O método onBindViewHolder pega um Produto e preenche os elementos visuais.

![alt text](resume.png)