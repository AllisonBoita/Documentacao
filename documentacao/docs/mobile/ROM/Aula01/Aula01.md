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

### Detalhes sobre a documentação e linguagem

A página da documentação pode apresentar informações e formatações diferentes dependendo da linguagem. Um exemplo disso é que a página em inglês, no momento em que o vídeo foi gravado, apresentava os seguintes benefícios:

Compile-time verification of SQL queries: Verificação de consultas SQL em tempo de compilação;

Convenience annotations that minimize repetitive and error-prone boilerplate code: Anotações convenientes que minimizam códigos repetitivos e sujeitos a erros;
Streamlined database migration paths: Caminhos simplificados para fazer migração de banco de dados.
Não se preocupe com as mudanças! Mesmo que não visto em vídeo, esses destaques por conta da linguagem serão abordados no decorrer do curso.


## Faça como eu fiz: Adicionando o Room

Na página da documentação, você terá acesso aos scripts necessários para instalar o Room no seu projeto Android. Em vídeo, utilizamos as seguintes dependências:

```kotlin
    dependencies {
        def room_version = "2.3.0"

        implementation "androidx.room:room-runtime:$room_version"
        kapt "androidx.room:room-compiler:$room_version"

        // demais dependências
    }
```

Sugerimos que utilize a mesma versão apresentada na aula para que tenha a mesma experiência apresentada em curso. Fique à vontade para usar a versão mais recente da documentação, porém, saiba que existe a chance de você encontrar problemas não esperados.

Após adicionar a biblioteca, adicione o plugin do kapt ('kotlin-kapt') para configurar o annotation processing do Kotlin. Em seguida, sincronize o projeto, confira se o processo de build é realizado com sucesso e tente acessar APIs do Room, como, por exemplo, a anotação androidx.room.Entity.

### Para saber mais: Sobre Annotation Processing

Como vimos, o Room utiliza a técnica de Annotation Processing (em português, processamento de anotações) para gerar o código fonte de baixo nível que se comunica com o SQLite a partir de metadados (anotações). Como o objetivo do curso é reutilizar esse recurso disponível em Java desde a versão 5, optamos por não apresentar mais detalhes sobre essa técnica.

Caso você tenha interesse em conhecer mais sobre Annotation Processing, como, por exemplo, quando usar e suas motivações, sugerimos a leitura [deste artigo da Mindworks (em inglês).](https://blog.mindorks.com/android-annotation-processing-tutorial-part-1-a-practical-approach/)