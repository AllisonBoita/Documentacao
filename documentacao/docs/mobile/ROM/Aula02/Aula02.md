## Faça como eu fiz: Criando a Entidade e DAO

[Conforme apresentado na documentação](https://developer.android.com/training/data-storage/room#sample-implementation), implemente o código dos componentes Entidade e DAO. Para isso, faça os seguintes ajustes:

Transforme o modelo produto em uma entidade:
Além da anotação @Entity, é necessário configurar a chave primária (@PrimaryKey).
Lembre-se de configurar a estratégia de auto incremento de ids.

Crie a interface ProdutoDao e anote-a com @Dao:
Adicione os comportamentos para buscar e salvar produtos.
Lembre-se de que o Room nos auxilia na escrita de consultas (queries) SQL, sendo assim, utilize as sugestões de auto complete para facilitar a implementação.

Nesta atividade, não há necessidade de rodar o projeto. Sendo assim, confira se implementou o código como esperado e prossiga para a próxima atividade.

## Faça como eu fiz: Criando o Database

[Seguindo o exemplo da documentação](https://developer.android.com/training/data-storage/room?hl=pt-br#sample-implementation), implemente o componente Database do Room. Para isso, faça o seguinte:

Crie uma classe abstrata que herde de RoomDatabase (O nome da classe fica a seu critério, em curso utilizamos a AppDatabase);
Em seguida, anote a classe com @Database e configure os parâmetros exigidos:
entities: envie um array com a referência da classe Produto;
version: crie a primeira versão do banco de dados, no caso, a 1;
Adicione o método abstrato que devolve a referência ProdutoDao.
Após aplicar todos os ajustes, faça o build do projeto com a opção Make Project (você pode acessar essa opção por meio do atalho Ctrl + F9) e confira se, ao finalizar o processo de build, o Room apresenta um problema para lidar com a property valor da classe Produto.