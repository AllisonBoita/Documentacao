## Inserindo Views na Activity

Dentro do onCreate() da Activity, crie um TextView e adicione uma mensagem de sua preferência, por exemplo, "Cesta de frutas".

Em seguida, chame o método setContentView() e envie o TextView como argumento.

Execute o App e confira se apresenta o resultado esperado.

###  Utilizando o arquivo de layout na Activity

Dentro do diretório res, crie um diretório do Android a partir da opção Android Resource Directory. Em seguida, selecione a opção layout no campo Resource type para que o AS crie um diretório de layout e, então, clique em OK.

Com o diretório layout criado, crie um arquivo de layout a partir da opção Layout Resource File, Então nomeie o arquivo como activity_main. Como vimos, o Root Element não é um valor que precisamos de atenção neste momento, porém, pode ser que ele mude dependendo da versão do Android Studio que esteja utilizando.

Para garantir a mesma visualização, utilize como Root Element o androidx.constraintlayout.widget.ConstraintLayout. Não é necessário modificar os demais campos. Clique em OK para criar o layout.

Caso o ConstraintLayout disponível tenha um nome de pacote diferente, mas que seja do androidx, você pode utilizar também.

Após criar o layout deve apresentar uma tela similar a essa:

Tela do Android Studio em visualização Split: o código está à esquerda e a visualização do layout, que está em branco, à direita.

Como vimos, a visualização de um arquivo de layout do Android apresenta 3 opções de visualização:

Code: Visualização do código fonte (XML)
Split: Visualização do código fonte e preview
Design: Visualização do kit de ferramentas para construção de layout pelo editor visual
Para um primeiro contato, geralmente utilizamos a opção Design por não exigir conhecimentos técnicos. Então, acesse a tela de Design e adicione um TextView a partir da paleta de views à esquerda:

Animação que mostra a mudança da opção de visualização de Split para Design, em que a visualização do layout em branco fica centralizada e sem o código. Em seguida, é inserido no layout da tela um TextView em que se lê “Cesta de frutas”

Para adicionar o TextView a partir da paleta, você precisa clicar e segurar antes de arrastar e soltar na tela.

Durante este teste, modifique o texto do TextView a partir da propriedade text dos atributos à direita.

Após realizar as modificações, dentro do onCreate() da MainActivity, adicione o layout por meio da chamada R.layout.activity_main (lembre-se de importar a classe R do pacote do seu projeto) como argumento da setContentView(). Execute o App e confira se ele apresenta o layout.