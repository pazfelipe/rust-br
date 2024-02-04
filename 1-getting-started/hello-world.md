# Linguagem de Programação Rust

[Lista de capítulos](/chapters.md) - [Primeiros Passos](./README.md) - Olá Mundo!

## Olá, Mundo!

Agora que você já instalou o Rust, é hora de escrever o seu primeiro programa. Muito comum, quando estamos aprendendo uma nova linguagem, escrever um pequeno programa que mostre o texto `"Olá, Mundo!"`, portanto, vamos fazer a mesma coisa aqui.

> Nota
> 
> Acredito que você já tenha alguma familiaridade com linhas de comando. Não importa como você está codificando, que ferramenta usando ou onde seu código está. Caso você prefira usar uma IDE (integrated development environment) ao invés de usar a linha de comando, sinta-se a vontade para usar sua IDE favorita. Muitas IDEs possuem algum nível de suporte ao Rust; verifique a documentação da sua IDE para mais detalhes. A equipe do Rust tem focado em disponibilizar um bom suporte às IDEs via `rust-analyzer`. Confira o [Apêndice D](https://doc.rust-lang.org/book/appendix-04-useful-development-tools.html) para mais detalhes.

## Criando um diretório de projeto

Você iniciará criando um diretório para guardar seu código em Rust. Não importa onde você vai salvar seu código, mas para os exercícios e projetos desse livro, recomendamos criar um diretório `projetos` no seu diretório `home` e manter todos os seus projetos nele.

Abra um terminal os seguintes comandos para criar o diretório `projetos` e um diretório para o projeto `Olám, Mundo!` dentro do diretório `projetos`.

```bash
$ mkdir ~/projects
$ cd ~/projects
$ mkdir hello_world
$ cd hello_world
```

Para o CMD do Windows, execute o comando:

```cmd
> mkdir "%USERPROFILE%\projects"
> cd /d "%USERPROFILE%\projects"
> mkdir hello_world
> cd hello_world
```

## Escrevedo e Executando um Programa Rust

A seguir, vamos criar um novo arquivo e chamá-lo de `main.rs`. Arquivos Rust sempre terminam com a extensão `.rs`. Se você estiver usando mais de uma palavra para nomear o arquivo, a convenção sugere usar um `underscore` (_) para separar as palavras. Por exemplo, use `hello_world.rs` ao invés de `helloworld.rs`.

Agora abra o arquivo `main.rs` que você acabou de criar e insira o código em `Lista 1-1`.

Nome do arquivo: `main.rs`

```rs
fn main() {
    println!("Olá, mundo!");
}
```

<sub><sub>Lista 1-1: Um programa que mostra `Olá, mundo!`.<sub><sub>

Salve o arquivo e volte para a janela do seu terminal navegando até o diretório `~/projetos/hello_world`. No Linux ou macOS, insira os seguintes para compilar e rodar o arquivo

```shell
$ rustc main.rs
$ ./main
Olá, mundo!
```

No Windows, insira o comando `.\main.rs` ao invés de `./main`

```cmd
> rustc main.rs
> .\main.exe
Olá, mundo!
```

Independente do seu sistea operacional, o texto `Olá, mundo!` deverá aparecer no terminal. Se você não vir essa saída, consulte novamente  página de [Soluções de Problemas](../1-getting-started/installation.md#solução-de-problemas) para ver meios que possam ajudar.

Se o texto `Olá, mundo!` for mostrado, parabéns! Você oficialmente escreveu um programa em Rust. Isso te dá um boas-vindas-programador Rust!

## Anatomia de um programa em Rust

Vamos rever esse programa `Olá, mundo!` em detalhes. Aqui está a primeira parte do quebra-cabeça:

```rs
fn main() {

}
```

Esta linha define uma função chamada `main`. A função `main` é especial: ela é sempre o primeiro código que roda em cada programa executável em Rust. Aqui, a primeira linha declara a função `main` que não possui parâmetros e retorna nada. Se houve parâmetros, eles iriam dentro de `()`.

O corpo da função está encapsulado dentro de `{}`. A linguagem Rust requer _chaves_ `{}` em cada corpo de função. É uma boa prática colocar a chave de abertura na mesma linha da declaração da função, adicionando um espaço em branco entre eles.

> Nota: se você quiser manter um padrão de estilo em todos os seus projetos Rust, você pode estar usando um formatador automático chamado `rustfmt` para formatar o seu código de maneira específica (mais sobre `rustfmt` no [Apêndice D](https://doc.rust-lang.org/book/appendix-04-useful-development-tools.html)). O time do Rust incluiu essa ferramente com a distribuição padrão do Rust, assim como em `rustc`, isso já deveria estar instalado em seu computador.

O corpo da função `main` mantém o seguinte código

```rs
    println!("Hello, world!");
```

Todo o trabalho desse pequeno programa é feito nessa linha: ele imprime textos na tela. Há quatro importantes detalhes para notar aqui:

Primeiro, a identação do Rust é feito com 4 espaços, não com `tabs`.

Segundo, `println!` chamada uma macro do Rust. Se tivesse chamado uma função, teria sido escrito `println` (sem o `!`). Vamos discutir macros em Rust em maiores detalhes no capítulo 19. Por hora, você só precisa saber que usar `!` significa que você está chamando uma _macro_ ao invés de uma função normal e que macros nem sempre seguem as mesmas regras de uma função.

Terceiro, você viu o texto `Olá, mundo!`. Passamos essa texto como um argumento para `println!`, e o texto é mostrado na tela.

Quarto, terminamos a linha com um ponto e vírgula `;`, que indica que esta expressão terminou e a próxima está para começar. A maioria das linhas de código em Rust terminam com ponto e vírgula.

## Compilar e Executar são passos separados

Você acabar de executar um programa fresquinho, para isso, vamos examinar cada passo nesse processo.

Antes de executar um programa em Rust, você precisa compilá-lo usando o compilador do Rust através do comando `rustc` e informando o nome do arquivo, como no exemplo:

```rs
$ rustc main.rs
```

Se você tiver alguma experiência com C ou C++, você vai notar é que muito similar ao `gcc` ou `clang`. Depois de compilar com sucesso, Rust cria um executável binário.

No Linux, macOS, e no Windows PowerShell, você consegue listar o executável rodando o comando `ls`:

```shell
$ ls
main  main.rs
```

No Linux e macOS, você vai ver dois arquivos. Com o PowerShell do Windows, você vai ver os mesmos 3 arquivos que você viria com o CMD. Com o CMD do Windows, insira o comando abaixo:

```cmd
> dir /B %= the /B option says to only show the file names =%
main.exe
main.pdb
main.rs
```

Isso mostra o arquivo do código fonte com a extensão `.rs`, o arquivo executável (_main.exe_ no Windows e _main_ nas demais plataformas), e, quando estiver usando o Windows, um arquivo contendo informaçÕes de debug com a extensão `.pdb`. A partir daqui, rode o arquivo _main_ ou _main.exe_, dessa maneira:

```shell
$ ./main # or .\main.exe no Windows
```

Se o seu `main` for o seu programa `Olá, mundo!`, essa linha mostrará `Olá, mundo!` no seu terminal.

Se você estiver mais familiarizado com linguagens dinâmicas como Ruby, Python ou Javascript, talvez você não esteja habituado em compilar e rodar o programa em diferentes passos. Rust é uma linguagem compilada antecipadamente, o que significa que você pode compilar o programa e compartilhar seu executável com qualquer pessoa, e ela pode rodar o programa sem nem ter o Rust instalado. Se você compartilhar um arquivo `.rb`, `.py` ou `.js`, vai ser preciso ter instalado `Ruby`, `Python` ou `Javascript` (respectivamente). Mas nessas linguagens, você precisa apenas de um comando para compilar e executar o seu programa. Tudo é uma questão de troca no design da linguagem.

Compilar com `rustc` é interessante para pequenos programas, mas a medida que seu projeto cresce, você vai querer ter mais opções de gerenciamento e tornar o processo mais fácil. No próximo capítulo vamos introduzir a ferramenta `Cargo`, cuja a qual facilitará escrever programas reais em Rust.
