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

