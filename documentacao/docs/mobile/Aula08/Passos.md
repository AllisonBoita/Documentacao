Ajustando a atualização dos produtos

Modifique o código da MainActivity e aplique as seguintes técnicas:

Renomeie a Activity para ListaProdutosActivity e o arquivo de layout para activity_lista_produtos.
Extraia métodos de códigos que fazem uma ação, por exemplo, a configuração do RecyclerView ou FAB.
Ajuste o comportamento do RecyclerView e FAB para que sejam criados no onCreate() e o adapter seja uma property. (É necessário transformar o DAO em property também).
Faça com que o Adapter atualize o RecyclerView no onResume(). Para isso, implemente o método de atualização e envie os produtos para ele.
Após finalizar os ajustes, teste o App e confira se funciona como o esperado.

Ajustando formulário e ids dos layouts

Finalize a refatoração do projeto ajustando o código do formulário com extrações de métodos da mesma forma que foi feito na lista de produtos.

Além dessa modificação, também ajuste os ids dos layouts para que seja únicos seguindo o seguinte padrão:

activity_nome_da_activity_id um exemplo de nomeação activity_lista_produtos_recyclerview
Após aplicar os ajustes teste o App e confira se funciona como esperado.

## Diferenças entre recycler view e Binding

A diferença entre usar binding e acessar o RecyclerView diretamente com findViewById está principalmente na forma como você lida com as Views no código. Aqui vai um comparativo pra clarear:

✅ Usando View Binding
kotlin
Copiar
Editar
val binding = ActivityMainBinding.inflate(layoutInflater)
setContentView(binding.root)
binding.recyclerView.adapter = MeuAdapter()
🟢 Vantagens:
Segurança de tipo (type-safe): se o ID mudar ou for removido do layout, o erro aparece na compilação.

Sem necessidade de findViewById: o código fica mais limpo e direto.

Menos propenso a erros de NullPointerException, já que tudo vem já referenciado corretamente no binding.

Mais legível e moderno, seguindo boas práticas do Android moderno.

🔵 Usando findViewById diretamente
kotlin
Copiar
Editar
setContentView(R.layout.activity_main)
val recyclerView = findViewById<RecyclerView>(R.id.recyclerView)
recyclerView.adapter = MeuAdapter()
🟡 Vantagens:
Funciona bem em projetos simples ou antigos, sem necessidade de configurar o View Binding.

Mais manual e explícito, o que pode ajudar iniciantes a entender a estrutura da tela.

🔴 Desvantagens:
Mais verboso: você precisa escrever findViewById para cada componente.

Mais sujeito a erros: se mudar o ID ou esquecer de cast, o app pode crashar em runtime.

Sem checagem de tipos automática, o que pode levar a bugs silenciosos.

📝 Em resumo:
Recurso	View Binding	findViewById
Segurança de tipo	✅ Sim	❌ Não
Facilidade de uso	✅ Mais simples	❌ Mais verboso
Erros em tempo de compilação	✅ Sim	❌ Só em runtime
Compatível com layouts complexos	✅ Sim	✅ Sim
