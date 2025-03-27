## Implementando Activity

Não existe main, mas sim activity

Uma activity é o ponto de entrada dentro do aplicativo.

Uma activity possui:
 
- View: Layout para usuário
- Lógica: Programação

### Criando Activity

Pasta Java > Pacote de prod > ALT + INSERT > Java Class > "MainActivity"

Adicionamos o extends da Activity e importamos essa classe.

--

Vamos agora para manifests > AndroidManifest

No application é onde registramos as activitys, icones e nome do aplicativo.

Nele vamos abrir a tag e adicionar o seguinte

<activity android:name=".MainActivity">
    <intent-filter>
        <action android:name"android.intent.action.MAIN"
        <category android:name="android.intent.category.LAUNCHER"
    <intent-filter>
</activity>

### Testando inicialização do APP

A activity possui um ciclo de vida. Esse ciclo indica o momento em que a activity é criada, por exemplo.

Na nossa MainActivity.kt

override fun onCreate(savedInstanceState: Bundle?)
super.onCreate(savedInstanceState) 

Toast.makeText(this, "Bem vindo", Toast.LENGTH_SHORT).show()

### Adicionando views na activity.

Vamos remover o toast e adidionar o seguinte:

val view = View(this) <!-- aqui ele pede um argumento necessário. -->
setContentView(view)

<!-- Para comportamentos mais específcios, por exemplo. adicionar texto

usamos a TextView. -->

view.setText("Olá Mundo")

### Layout - Adicionando tudo em um arquivo exclusivo.

Todo o código e views são adicionadas em um local e são apenas carregadas na activity

./res

drawable: permite colocar imagens
mipmap: versões de icones diferentes
values: cores disponíveis configuradas pro app
strings: valores em strings que não são modificados.
themes: define qual o tema padrão e o tema escuro.

### Criando o layout da activity

ALT + INSERT

android resource director
selecionamos o layout.

ALT + INSERT dnv

layout resource file

1. Primeiro colocamos o nome (padrão activity_main...)
2. Root Element: padrão
3. oK

Arquivo criado.

### Estilizando layout.

Podemos clicar, arrastar e soltar.
No text podemos modificar o texto (ao invés de fazer direto na activity)

Voltando na activity vamos carregar o que fizemos no layout.

setContentView(R.layout.activity_main) <!-- Carregando o layout -->
<!-- Podemos apagar o texto adicionado anteriormente. -->

### Evoluindo com layout

Existe uma serie de regras para atender o que se espera.

Todos os componentes são views: desde a constraint layout até o textview...

1. Sempre teremos um elemento raiz.

Uma view não pode ter outras views.
Para que a gente consiga utilizar uma view que receba outras devemos usar a ViewGroup

ConstraintLayout é uma viewGroup

![alt text](image-1.png)

<!-- Constraint layout -->

#### Posicionando view

Podemos arrastar a view para onde desejarmos.

Qualquer view que não tenha regra e fique dentro de uma viewgroup (constraint) ele fica em vermelho.

#### Implementando namespace Layout

Usar o método split no android studio, para ver o que acontece debaixo dos panos.

Utilizamos o namespace app para chamar atributos específicos da View.

Para apresentar o conteúdo apenas no preview, utilizamos o tools.

android:text="Cesta de frutas"

### Implementando Layout

o match_parent cresce em relação ao tamanho do Posicionando

o wrap_content cresce em relação ao conteudo

--

Quando não houver nenhuma constraint ele sempre fica grudado no topo.

para separar adicionamos o seguinte:

app:layout_constraintTop_toBottomOf="@id/textView"

para adicionar o id adicionamos o 

1. android:id="@+id/textView"

--

Quando se mudar algum ID utilizar atalho SHIFT F6 e ele renomeia em todos os pontos.

### Aplicando margin

Se trabalhamos com px ficamos sucessiveis a dispositivos variados. Podem apresentar diferenças.

DP = Densidade de pixels

significa que será uma unidade que fará um "pixel virtual". ou seja, ele calcula automaticamente pixels para se adaptar.

### Aplicando textSize

Para o texto usamos o SP para aumentar ou não o tamanho da fonte.

É bem semelhante ao DP porém esse SP facilita algumas questões de acessibilidade.