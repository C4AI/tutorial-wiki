# tutorial-wiki

Este repositório serve para continuamente criar uma documentação que forneça uma visão geral sobre o MediaWiki, tal como o que é essa ferramenta, como ela funciona, como instalar e como usá-la.

A documentação possui, no branch `main`, arquivos escritos em MarkDown, que são convertidos para HTML usando o [jupyter-book](https://jupyterbook.org/) e que são disponibilizados usando o Github Pages.

## Estrutura

O repositório segue, basicamente, a estrutura abaixo, com o detalhe de que as pastas `Imagens`, `.doctrees` e `html` tiveram seus conteúdos ocultados.

```bash
│   1_Introducao.md
│   logo.png
│   README.md
│   requirements.txt
│   _config.yml
│   _toc.yml
│
├─── 2_SobreMediaWiki
│       2_0_SobreMediaWiki.md
│       2_1_LayoutSkins.md
│       2_2_Estrutura.md
│       2_3_Formato.md
│       2_4_Extensoes.md
│       2_5_Templates.md
│       2_6_ExportImport.md
│       2_7_GruposPermissoes.md
│
├─── 3_InstalacaoConfiguracao
│       3_0_InstalacaoConfiguracao.md
│
├─── 4_ContasNaWiki
│       4_0_ContasNaWiki.md
│
├─── 5_EscrevendoNaWiki
│       5_0_EscrevendoNaWiki.md
│       5_1_CriarPagina.md
│       5_2_EdicaoVisualMarkup.md
│
├─── Imagens
│
└─── _build
    ├─── .doctrees
    │
    └─── html
```

* O arquivo `1_Introducao.md` é a primeira página da documentação.
* O arquivo `logo.png` é a logo que aparece no canto superior esquerdo da documentação
* Este arquivo `README.md` explica sobre o repositório e sobre as ferramentas usadas
* O arquivo `requirements.txt` possui pacotes que são necessários para executar códigos usados ao longo do livro. Como este livro serve somente para documentação, não há código e, portanto, o único requisito é o próprio `jupyter-book`
* O arquivo `_config.yml` possui configurações como título do livro, autor, arquivo de logo e opções relacionadas ao github
* O arquivo `toc.yml` possui a estrutura da Table Of Contents (TOC) do livro e o formato dele, que, no caso, é um livro
* A pasta `2_SobreMediaWiki` contém as páginas do capítulo de explicação sobre o MediaWiki
* A pasta `3_InstalacaoConfiguracao` contém as páginas do capítulo sobre instalação e configuração
* A pasta `4_ContasNaWiki` contém as páginas do capítulo sobre contas de usuários
* A pasta `5_EscrevendoNaWiki` contém as páginas do capítulo com tutoriais mais aplicados
* A pasta `Imagens` possui as imagens utilizadas no livro
* A pasta `build` possui a subpasta `html`, que é a versão compilada para *web* do livro, a qual está no Github Pages

## Contribuindo com o tutorial

O objetivo é que esta documentação possa ser continuamente melhorada, seja clonando o repositório de forma remota ou editando os arquivos diretamente no github.com.

### Clonando o repositório

Caso prefira escrever a documentação no editor de texto do seu computador, será necessário

* Clonar o repositório
* Instalar as dependências
* Após fazer edições, fazer a build e atualizar o repositório e o Github Pages

#### Clonar o repositório

Para clonar, é necessário antes ter o [Git](https://git-scm.com/) instalado.

Estando no diretório do seu computador para a qual deseja que a pasta do repositório seja clonada, faça

```
git clone https://github.com/rodtav/tutorial-wiki.git
```

Com isso, o repositório terá sido clonado para o seu computador. Nesse caso, o `remote` de onde você clonou recebe o nome de `origin`.

#### Instalar os pacotes

Com o repositório clonado, pode-se fazer edições nos arquivos usando o seu editor de preferência. Após isso, será necessário atualizar o repositório online e o Pages. Para isso, há duas opções:

* No seu computador, criar a nova build usando o `jupyter-book`, atualizar os arquivos no `remote` com o Git e subi-la para o Github Pages com o `ghp-import`
* No seu computador, somente atualizar os arquivos no `remote` e, no github.com, criar a build e atualizar o Pages.

##### Primeira opção

* É necessário o gerenciador de pacotes *pip*, que é instalado junto com o [Python](https://www.python.org/downloads/). Tome cuidado para que a versão do Python seja para o mesmo número de bits que o seu computador. Baixar um Python de 32 bits em um computador de 64 bits pode não funcionar bem e vice-versa
* É necessário o gerenciador de pacotes *cargo*, que pode ser instalado junto com o [Rust](https://www.rust-lang.org/tools/install)
* No terminal, faça
    - `pip install -U jupyter-book`
* Para compilar o livro em HTML, faça
    - `jb build --all .`
* Para atualizar, o repositório remoto, faça
    - `git add .`
    - `git commit -m "Explicação das edições"`
    - `git push`
* Para atualizar o Pages, faça
    - `ghp-import -n -p -f _build/html`

##### Segunda opção

No terminal do seu computador, faça

* `git add .`
* `git commit -m "Explicação das edições"`
* `git push`

Agora, vá até o repositório online em github.com e faça

* Na guia Actions, seleciona `deploy-book`
* Clique em *Run workflow*
* Na janela, selecione o branch `main`
* Clique em *Run workflow*

### Editando no github.com

No repositório online, você pode criar novos arquivos e editar os arquivos que já existem. Ao final de cada edição, será necessário fazer o commit da edição. Por fim, quando desejar publicar as edições, faça

* Na guia Actions, seleciona `deploy-book`
* Clique em *Run workflow*
* Na janela, selecione o branch `main`
* Clique em *Run workflow*
