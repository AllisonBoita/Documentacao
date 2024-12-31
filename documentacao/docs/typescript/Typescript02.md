# 🔧 Modificando o TypeScript Compiler

O **TypeScript Compiler** (ou **`tsc`**) é a ferramenta que converte o código TypeScript em JavaScript. Ele pode ser configurado de várias maneiras para adaptar o processo de compilação às necessidades de seu projeto. Além de usar a configuração padrão, é possível modificar e personalizar o comportamento do compilador por meio do arquivo **`tsconfig.json`**.

---

## ⚙️ Configurando o `tsconfig.json`

O arquivo **`tsconfig.json`** é um arquivo de configuração utilizado para controlar como o compilador TypeScript deve se comportar ao compilar o código. Ele permite configurar várias opções, como o diretório de saída, os arquivos que devem ser incluídos no projeto, entre outras opções.

### Exemplos de opções de configuração no `tsconfig.json`:

- **`compilerOptions`**: Define as opções do compilador, como a versão do **ECMAScript** que o código deve ser transpilado, o diretório de saída, entre outros.

---

## 🔨 Modificando o Processo de Compilação

Além de usar as opções do **`tsconfig.json`**, você pode modificar o comportamento do compilador com o uso de plugins ou outras ferramentas externas:

- **Plugins de TypeScript**: Existem plugins que podem ser usados para estender a funcionalidade do compilador, como o **`ts-plugin`** para linting e formatação de código.
- **Ferramentas de construção**: Ferramentas como **Webpack**, **Rollup** ou **Gulp** podem ser usadas em conjunto com o TypeScript para automatizar o processo de compilação e adicionar outras funcionalidades, como minificação e bundle de módulos.

---

## ✅ Conclusão

O **TypeScript Compiler** é altamente configurável, e você pode adaptar o processo de compilação às necessidades do seu projeto por meio do arquivo **`tsconfig.json`** ou modificando-o com plugins e ferramentas externas.
