# Documentação da Aula de Introdução ao Desenvolvimento Android

## O que você aprendeu nesta aula

### O que é o Android, plataformas e benefícios de criar um App Android

O Android é um sistema operacional baseado em Linux focado em oferecer uma interface de interação com o usuário por meio de toques e gestos. Além de rodar em smartphones e tablets, Apps Android podem rodar em:

- Smartwatches (Wear OS)
- Smart TVs
- Automóveis
- Notebooks com Chrome OS
- Dispositivos IoT

Ao desenvolver um App Android, você tem a possibilidade de alcançar bilhões de pessoas por meio da Play Store, e ainda pode utilizar recursos do sistema e dispositivos, como câmeras, GPS, sensores e conectividade, para melhorar a experiência do usuário.

### Como preparar o ambiente e criar um projeto Android

Na aula, aprendemos a instalar e inicializar a IDE oficial da Google, o **Android Studio**. Durante a instalação, também instalamos o **Android SDK**, que é necessário para acessar o framework Android.

### O que é uma Activity e como configurar uma do zero

Diferente de muitos programas, no Android não temos um método `main` para rodar o App. O ponto de entrada de um App Android é a **Activity**, que é um componente do Android que apresenta a tela para o usuário, utilizando Views e lógica.

As **Activities** são criadas a partir de uma classe Kotlin ou Java que herda da classe `Activity`. Para que o sistema Android reconheça a Activity, ela precisa ser registrada no arquivo de manifesto, o **AndroidManifest.xml**.

### O que é o AVD Manager e como criar dispositivos virtuais (emuladores)

Para executar um App Android, precisamos de um dispositivo que opere o Android. No nosso contexto, esse dispositivo pode ser um smartphone ou tablet. O Android Studio oferece o **AVD (Android Virtual Device) Manager**, que permite criar dispositivos virtuais, também conhecidos como **emuladores**, que rodam o sistema Android.

Através do AVD Manager, podemos selecionar o modelo do dispositivo e a imagem do sistema Android que desejamos emular, possibilitando a execução e simulação de dispositivos Android diretamente no computador.

### Como rodar um App Android em dispositivos físicos ou virtuais

Além de usar emuladores, temos a opção de executar Apps em **dispositivos físicos** que rodam Android, como smartphones ou tablets. Para que isso seja possível, é necessário:

1. Ativar o **modo de desenvolvedor** no dispositivo físico.
2. Habilitar o **modo de depuração (debug)**.
3. Conectar o dispositivo ao computador via cabo USB.

Com isso, é possível rodar e testar o App diretamente no dispositivo físico.
