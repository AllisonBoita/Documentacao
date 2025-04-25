# 📱 Desenvolvimento Mobile com Kotlin/Java - Conceitos Importantes

## 🧱 Componentes Fundamentais

### 1. **Activity**
- Representa uma **tela** da aplicação.
- Cada Activity é uma entrada independente na interface do usuário.

### 2. **Fragment**
- Um componente **modular** de uma Activity.
- Pode ser reutilizado em várias telas.
- Ideal para interfaces dinâmicas ou adaptativas.

### 3. **ViewModel**
- Contém a lógica e dados da interface.
- Sobrevive a mudanças de configuração (como rotação da tela).
- Facilita separação de responsabilidades.

### 4. **LiveData / StateFlow**
- Permitem observar mudanças de dados.
- `LiveData` é lifecycle-aware (segue o ciclo de vida da tela).
- `StateFlow` vem da API de corrotinas, ideal para fluxos reativos.

## 🧠 Arquitetura

### 5. **DAO (Data Access Object)**
- Interface usada para interagir com o banco de dados via Room.
- Usa anotações como `@Query`, `@Insert`, `@Delete`, etc.

```kotlin
@Dao
interface UserDao {
    @Query("SELECT * FROM users")
    fun getAllUsers(): List<User>
}
```

### 6. **Repository**
- Camada entre o ViewModel e os dados.
- Responsável por centralizar o acesso ao banco ou API.

### 7. **MVVM (Model-View-ViewModel)**
- Arquitetura padrão moderna no Android.
- **Model**: dados e lógica (DAO, API).
- **ViewModel**: lógica da UI e dados.
- **View**: Activity ou Fragment, que observa os dados.

## 🌐 Requisições de Rede

### 8. **Retrofit**
- Biblioteca da Square para chamadas HTTP.
- Simples, segura e poderosa.

**Dependências:**
```gradle
implementation 'com.squareup.retrofit2:retrofit:2.9.0'
implementation 'com.squareup.retrofit2:converter-gson:2.9.0'
```

**Exemplo:**
```kotlin
interface ApiService {
    @GET("users")
    suspend fun getUsers(): List<User>
}

val retrofit = Retrofit.Builder()
    .baseUrl("https://api.seuservidor.com/")
    .addConverterFactory(GsonConverterFactory.create())
    .build()

val api = retrofit.create(ApiService::class.java)

viewModelScope.launch {
    val users = api.getUsers()
}
```

### 9. **Gson / Moshi**
- Bibliotecas usadas para converter JSON ↔ Objetos.
- Gson é mais popular com Retrofit.

## 💾 Persistência de Dados

### 10. **Room**
- ORM oficial do Android baseado em SQLite.
- Trabalha com DAOs e gera código automaticamente.

```kotlin
@Entity
data class User(
    @PrimaryKey val id: Int,
    val name: String
)
```

### 11. **SharedPreferences / DataStore**
- Para armazenar pares chave-valor.
- `DataStore` é a alternativa moderna e recomendada ao SharedPreferences.

## 🎯 Outros Conceitos Importantes

### 12. **ViewBinding**
- Substitui o `findViewById` com segurança e tipagem.

**Habilitar:**
```gradle
android {
    buildFeatures {
        viewBinding = true
    }
}
```

**Exemplo:**
```kotlin
private lateinit var binding: ActivityMainBinding

override fun onCreate(savedInstanceState: Bundle?) {
    super.onCreate(savedInstanceState)
    binding = ActivityMainBinding.inflate(layoutInflater)
    setContentView(binding.root)

    binding.textView.text = "Olá, ViewBinding!"
}
```

### 13. **DataBinding**
- Permite associar dados diretamente no XML.

```xml
<TextView
    android:text="@{user.name}" />
```

### 14. **Navigation Component**
- Gerencia navegação entre Fragments.
- Define rotas e ações em um `nav_graph.xml`.

### 15. **Coroutines**
- Programação assíncrona de forma simples.
- Ideal para Retrofit, Room, delay, etc.

```kotlin
viewModelScope.launch {
    val result = repository.getData()
}
```

### 16. **Dependency Injection (Hilt / Koin)**
- Facilita a injeção de dependências como ViewModel, Repository etc.
- `Hilt` é o padrão oficial da Google.

## 🧪 Testes

### 17. **JUnit**
- Framework padrão para testes unitários.

### 18. **Espresso**
- Ferramenta para testes de UI.

## 🔄 Ciclo de Vida

- `onCreate()`, `onStart()`, `onResume()`, `onPause()`, `onStop()`, `onDestroy()` são métodos chamados em momentos diferentes da Activity/Fragment.
- Entender isso é essencial para evitar memory leaks e falhas.

## ⚙️ Gradle

- Sistema de build.
- Define versões, plugins, dependências.

```gradle
dependencies {
    implementation 'androidx.lifecycle:lifecycle-viewmodel-ktx:2.6.1'
    implementation 'com.squareup.retrofit2:retrofit:2.9.0'
    ...
}
```

## 🔐 Headers com Retrofit (Ex: Token JWT)

**Header por chamada:**
```kotlin
@GET("perfil")
suspend fun getPerfil(@Header("Authorization") token: String): Perfil
```

**Header global com Interceptor:**
```kotlin
val client = OkHttpClient.Builder()
    .addInterceptor { chain ->
        val request = chain.request().newBuilder()
            .addHeader("Authorization", "Bearer $token")
            .build()
        chain.proceed(request)
    }
    .build()
```