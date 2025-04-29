## Faça como eu fiz: Criando a Entidade e DAO

[Conforme apresentado na documentação](https://developer.android.com/training/data-storage/room#sample-implementation), implemente o código dos componentes Entidade e DAO. Para isso, faça os seguintes ajustes:

Transforme o modelo produto em uma entidade:
Além da anotação @Entity, é necessário configurar a chave primária (@PrimaryKey).
Lembre-se de configurar a estratégia de auto incremento de ids.

Crie a interface ProdutoDao e anote-a com @Dao:
Adicione os comportamentos para buscar e salvar produtos.
Lembre-se de que o Room nos auxilia na escrita de consultas (queries) SQL, sendo assim, utilize as sugestões de auto complete para facilitar a implementação.

Nesta atividade, não há necessidade de rodar o projeto. Sendo assim, confira se implementou o código como esperado e prossiga para a próxima atividade.
