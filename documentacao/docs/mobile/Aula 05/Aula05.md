### Criando nova activity

Crie a Activity para o formulário de produto a partir do AS. Para isso, acesse diretório app do projeto e utilize o atalho Alt + Insert para aparecer a opção New, então, filtre/encontre a opção Activity, clique nela e escolha a opção Gallery.

Entre as opções de Activity, escolha opção Empty Activity ou similar, e clique em Next. Agora preencha as seguintes informações da Activity:

Nome da Activity: FormularioProdutoActivity
Aceite a configuração para gerar layout e mantenha o padrão de nome sugerido activity_formulario_produto
Marque a Activity para ser a launcher do App para testar o formulário ao executar o App
Configure o pacote para que seja o br.com.alura.orgs.ui.activity
Mantenha a linguagem Kotlin e source set main
Após preencher as informações, clique em Finish. Após o AS finalizar o processo de build, dentro da FormularioProdutoActivity, importe a classe R caso ela não esteja importada. Então, execute o App e confira se apresenta a Activity de formulário como esperado.

### Gradle Scripts

Build Tool dos projetos android

Build.gradle (projetc): Arquivo principal de todo o projeto
Build.gradle (app): um módulo (app) de todo nosso projeto

### Nesta aula, você aprendeu:

- Como criar Activities com o AS

Ao criar uma Activity com o AS, evitamos fazer manualmente tanto a criação da classe em Kotlin e o arquivo de layout quanto a configuração no arquivo de manifesto do Android.

- Diferenças entre bibliotecas do SDK do Android e AndroidX

Ao desenvolver para Android temos a necessidade de dar suporte para diferentes versões do sistema operacional, porém, para que isso seja possível, precisamos utilizar bibliotecas que são capazes de garantir a compatibilidade entre as versões do Android, no caso, as bibliotecas do AndroidX.

- Projetos Android utilizam o Gradle como Build Tool

Ao criar um projeto Android com o AS, é criado um projeto em Gradle com plugins, dependências e configurações para o ambiente do Android. Toda essa responsabilidade de build é do Gradle, que é uma Build Tool muito poderosa que, além de fazer as configurações gerais de build, também oferece suporte mais avançado como o projeto em multi-módulos.

- Configurar arquivos de build para adicionar dependências no projeto

Além de acessar recursos disponíveis do SDK do Android, em um projeto Android, temos acesso a bibliotecas externas que são adicionadas e configuradas a partir do Gradle.

- Implementar uma tela de formulário

Além de implementar telas que apenas apresentam o conteúdo, como a lista de produtos, implementamos também telas que recebem informações do usuário, como um formulário com EditText e Button.

- Ajustar os editores de texto para melhorar a experiência

Ao utilizar EditText, podemos identificar qual campo ele representa a partir de dicas e também configurar o tipo de entrada mais adequado para os possíveis valores do campo.

- Configurar ação de clique em View

Além de escrever códigos que são executados apenas uma vez no onCreate() da Activity, podemos implementar listeners nas Views para adicionar códigos em ações, como o listener de clique em um Button.