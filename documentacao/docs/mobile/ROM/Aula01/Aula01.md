O android não consegue manter as alterações salvas ao fechar/abrir o app.

Armazenamento especifico: arquivos que somente o aplicativo acessa.

Armazenamento compartilhado: outros aplicativos conseguem acessar

Preferencias: armazena apenas tipos primitivos em pares de chave-valor

Banco de dados: só o app tem acesso e temos acesso usando a persistencia Room

--

Neste caso vamos usar o banco de dados com a [biblioteca Room](https://developer.android.com/training/data-storage/room)

![alt text](image.png)

## Para saber mais: Banco de dados com SQLite

Como vimos, o Room é uma biblioteca com o objetivo de abstrair a implementação de banco de dados com o SQLite.

Porém, isso não significa que não é possível implementar a solução de banco de dados sem o Room! Caso você tenha interesse nesse tipo de implementação, [você pode seguir as instruções de implementação do SQLite da documentação.](https://developer.android.com/training/data-storage/room?hl=pt-br)

É extremamente importante ressaltar que implementar um banco de dados com a API do SQLite não é recomendado, portanto, utilize por curiosidade ou fins didáticos. Se preferir, você pode [consultar o código de amostra](https://developer.android.com/training/data-storage/sqlite?hl=pt-br) apresentado em vídeo.