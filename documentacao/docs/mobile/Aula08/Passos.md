Ajustando a atualização dos produtos

Modifique o código da MainActivity e aplique as seguintes técnicas:

Renomeie a Activity para ListaProdutosActivity e o arquivo de layout para activity_lista_produtos.
Extraia métodos de códigos que fazem uma ação, por exemplo, a configuração do RecyclerView ou FAB.
Ajuste o comportamento do RecyclerView e FAB para que sejam criados no onCreate() e o adapter seja uma property. (É necessário transformar o DAO em property também).
Faça com que o Adapter atualize o RecyclerView no onResume(). Para isso, implemente o método de atualização e envie os produtos para ele.
Após finalizar os ajustes, teste o App e confira se funciona como o esperado.