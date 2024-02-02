# Linguagem de Programção Rust

[Lista de capítulos](/chapters.md) - [Primeiros Passos](./README.md) - Instalação

## Instalação

O primeiro passo é instalar Rust. Vamos fazer a instalação através do `rustup`, uma ferramenta de linha de comando para gerenciar versões e ferramentas relacionadas ao Rust. Você vai precisar de uma conexão com a internet para fazer o download.

> Nota: se você preferir não usar `rustup` por alguma razão, por favor veja a página [Outros métodos para a instalação do Rust](https://forge.rust-lang.org/infra/other-installation-methods.html) para maiores informações

Os próximos passos farão a instalação da última versão estável do compilador do Rust. As garantias de estabilidade do Rust asseguram que todos os exemplos neste livro que compilam continuarão a funcionar mesmo com versões mais recentes do Rust. O `output` pode ser um pouco diferente entre versões uma vez que Rust está sempre melhorando mensagens de erros e alertas. Em outras palavras, qualquer versão mais recente ou estável do Rust que você instale seguindo esses passos deverá funcionar como o esperado com os exemplos desse livro.

> _Notação do comando de linha_
>
> Neste capítulo e durante todo o livro, vamos mostrar alguns comandos usados no terminal. Linhas que você vai precisar usar o terminal iniciam com $. Você não precisa digitar o $. Isto é apenas o terminal mostrando o início de cada comando. Linhas que não iniciam com $ geralmente mostram a saída do comando anterior. Aliás, exemplos específicos do PowerShell iniciarão com > ao invés de $.

## Instalando rustup no Linux ou macOS

Se você estiver usando Linux ou macOS, abra um novo terminal e insira o seguinte comando:

```shell
$ curl --proto '=https' --tlsv1.2 https://sh.rustup.rs -sSf | sh
```

Este comando fará o download de um script e iniciará a instalação do `rustup`, e este vai instalar a última versão estável do Rust. Talvez você vai precisar inserir sua senha para concluir a instalação. Se tudo ocorrer bem, a seguinte frase será mostrada:

```shell
Rust is installed now. Great!
```

Talvez você precise instalar um `linker`, que é um programa usado por Rust para juntar as saídas compiladas em um arquivo. Se você estiver tendo erros de `linker`, provavelmente terá que instalar um compilador `C`, e que geralmente já inclui um `linker`. Um compilador `C` também pode ser útil uma vez que muitos pacotes comuns do Rust dependem de algum código em `C` e precisão de um compilador.

No macOS, você pode estar instalando um compilador C rodando o comando:

```shell
$ xcode-select --install
```

Usuários de Linux geralmente instalam `GCC` ou `Clang`, dependendo da documentação da sua distribuição (distro). Por exemplo, se você estiver usando `Ubuntu` pode instalar o pacote `buidl-essentials`.

## Instalando rustup no Windows

No Windows, vá até a página [https://www.rust-lang.org/tools/install](https://www.rust-lang.org/tools/install) e siga as instruções para instalar Rust. Em algum momento da instalação, você vai receber uma mensagem explicando que você também vai precisar do `MSVC build tools` para o `Visual Studio 2013` ou posterior.

Para obter essas ferramentas de build, você vai precisar instalar o [Visual Studio 2022](https://visualstudio.microsoft.com/downloads/). Quando perguntado sobre quais itens instalar, inclua:

- Desktop Developmenet with C++
- The Windows 10 or 11 SDK
- Pacote do idioma de componentes em inglês, junto com algum outro pacote de idioma de sua escolha.

O restante desse livro usa comandos que funcionam em ambos `cmd.exe` e `PowerShell`. Se houver diferenças, explicarems qual usar.

## Solução de Problemas

Para se certificar de que você instalou corretamente Rust, abra um novo terminal e insira o comando:

```shell
$ rustc --version
```

Você deverá ver o número da versão, o hash do commit, a data do commit da última versão estável disponibilizada, no seguinte formato:

```shell
rustc x.y.z (abcabcabc yyyy-mm-dd)
```

Se você vir essa mensagem, você instalou Rust corretamente. Caso você não veja essa informação, verifique se o Rust está na sua variável de ambiente `%PATH%`.

No Windows CMD, use:

```shell
> echo %PATH%
```

No PowerShell, use:

```shell
> echo $env:Path
```

No Linux ou no macOS, use:

```shell
$ echo $PATH
```

Se tudo estiver correto e mesmo assim o Rust ainda não funcionar, há um monte de lugares que você pode obter ajuda. Veja como entrar em contato com os nossos `Rustaceans` (como nos chamamos carinhosamente) em nossa [comunidade](https://www.rust-lang.org/community).

## Atualizando e Desinstalando

Uma vez que o Rust tenha sido instalado via `rustup`, atualizar para uma versão mais nova é simples. Abra um novo terminal e execute o seguinte comando:

```shell
$ rustup update
```

Para desinstalar o Rust e o `rustup`, execute o seguinte comando:

```shell
$ rustup self uninstall
```

## Documentação local

A instalação do Rust também inclui uma cópia local da documentação para você poder lê-la offiline. Rode `rustup doc` para abrir a documentação local no seu navegador.

Em qualquer momento que um tipo ou função for disponibilizada pela biblioteca padrão e você não estiver certo sobre o que ela faz ou como usar, use a API de documentação para descobrir.
