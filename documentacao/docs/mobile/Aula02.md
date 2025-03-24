# Introdução à Linguagem Kotlin e Fundamentos do Android

## Kotlin
Kotlin é uma linguagem moderna e concisa que roda na JVM e é oficialmente suportada pelo Android para o desenvolvimento de aplicativos. Ela combina características de programação funcional e orientada a objetos, oferecendo maior segurança contra **NullPointerException**, suporte a **corrotinas** para operações assíncronas e uma sintaxe mais clara em comparação ao Java.

## Activity
Uma **Activity** representa uma única tela do aplicativo e é responsável por interagir com o usuário. Cada Activity é uma classe que herda de `AppCompatActivity` ou `Activity` e segue o **ciclo de vida** gerenciado pelo sistema Android.

### Ciclo de Vida da Activity:
- `onCreate()`: Inicializa a Activity.
- `onStart()`: Torna a Activity visível.
- `onResume()`: A Activity começa a interagir com o usuário.
- `onPause()`: Perde o foco, mas ainda pode ser visível.
- `onStop()`: A Activity não está mais visível.
- `onDestroy()`: A Activity é destruída e removida da memória.

## Layout
Os layouts definem a interface gráfica da aplicação e podem ser criados de duas formas:
1. **XML**: Arquivos na pasta `res/layout` descrevem a hierarquia de elementos visuais.
2. **Jetpack Compose**: Um framework declarativo para criar UI diretamente em Kotlin.

Exemplo de layout XML:
```xml
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical">

    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Olá, mundo!" />
</LinearLayout>
```

## Views

Uma View é qualquer componente visível na tela, como:

TextView → Exibe texto.

Button → Botão interativo.

ImageView → Exibe imagens.

EditText → Campo de entrada de texto.

### Manipulação de Views em Kotlin:

```xml
val textView: TextView = findViewById(R.id.textView)
textView.text = "Novo Texto"
```

## AndroidManifest.xml

O AndroidManifest.xml é um arquivo essencial que define:

- Activities do app.

- Permissões necessárias (ex.: acesso à câmera, internet).

- Nome do pacote e informações básicas do aplicativo.

Exemplo:

```xml
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    package="com.example.meuapp">
    
    <application
        android:allowBackup="true"
        android:theme="@style/Theme.MyApp">
        
        <activity android:name=".MainActivity">
            <intent-filter>
                <action android:name="android.intent.action.MAIN" />
                <category android:name="android.intent.category.LAUNCHER" />
            </intent-filter>
        </activity>

    </application>
</manifest>
```

## ViewGroups

Um ViewGroup é um contêiner para organizar várias Views. Ele define como os elementos são dispostos na tela.

### Principais ViewGroups:

- LinearLayout → Organiza elementos em linha ou coluna.

- RelativeLayout → Permite posicionamento relativo entre elementos.

- ConstraintLayout → Mais flexível, recomendado para UIs complexas.

- FrameLayout → Exibe uma única View por vez.

Exemplo de LinearLayout:

```xml
<LinearLayout
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical">

    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Exemplo de ViewGroup" />

</LinearLayout>
```

## Construção de layout

- Todos os componentes são views.

- Pode haver somente uma view raiz. Aqui no caso ela não pode receber outras views.

- Para isso devemos usar a viewGroup

## O que aprendemos?

Nesta aula, você aprendeu:

- Adicionar Views na Activity

Para apresentar o conteúdo visual, as Activities utilizam View. Para inserir Views na Activity precisamos sobrescrever métodos do ciclo de vida, como o de criação (onCreate()) e enviar a View como argumento do método setContentView().

- Quais são os diretórios de recurso do Android

Além de código fonte para Kotlin/Java, os projetos Android também disponibilizam outros diretórios de recursos, como drawable, mipmap e value etc.

- Criar arquivos de layout

Além de criar Views diretamente no código da Activity, somos capazes de criar arquivos de layout focados para apresentar o conteúdo visual da Activity.

- Visualizar o layout pelo código fonte (XML) e pelo editor visual

Diferente da visualização de um arquivo de código-fonte Kotlin ou Java, arquivos de layout do Android apresentam 3 possibilidades de visualização do layout: Code, Split e Design. A partir delas podemos acessar apenas o código, o código com preview ou o preview com ferramentas de editor visual, respectivamente.

- Editar o layout e carregar na Activity

Além de visualizações diferentes para arquivos de layout, o Android Studio permite a edição em ambas as visualizações. Também, podemos carregar o arquivo de layout a partir da classe R (que dá acesso ao conteúdo do res), enviando para o setContentView() o nome do layout.

- Teoria da construção de layouts

Ao construir layouts no Android, temos acesso a Views e ViewGroups que permitem construir uma árvore de Views.

- Importância de utilizar ViewGroup na construção de layouts

Para que seja possível criar uma árvore de Views, precisamos de ViewGroups que podem receber uma ou mais View/ViewGroup. Uma View não pode receber outra View/ViewGroup como filha.
