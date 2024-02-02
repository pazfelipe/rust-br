# Linguagem de Programção Rust

## Instalacão

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

