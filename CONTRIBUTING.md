# Contribuindo

O objetivo é que esta documentação possa ser continuamente melhorada, seja clonando o repositório de forma remota ou editando os arquivos diretamente no github.com.

## Clonando o repositório

Caso prefira escrever a documentação no editor de texto do seu computador, será necessário

* Clonar o repositório
* Instalar as dependências
* Após fazer edições, fazer a build e atualizar o repositório e o Github Pages

### Clonar o repositório

Para clonar, é necessário antes ter o [Git](https://git-scm.com/) instalado.

Estando no diretório do seu computador para a qual deseja que a pasta do repositório seja clonada, faça

```
git clone https://github.com/rodtav/tutorial-wiki.git
```

Com isso, o repositório terá sido clonado para o seu computador. Nesse caso, o `remote` de onde você clonou recebe o nome de `origin`.

### Instalar os pacotes

Com o repositório clonado, pode-se fazer edições nos arquivos usando o seu editor de preferência. Após isso, será necessário atualizar o repositório online e o Pages. Para isso, há duas opções:

* No seu computador, criar a nova build usando o `jupyter-book`, atualizar os arquivos no `remote` com o Git e subi-la para o Github Pages com o `ghp-import`
* No seu computador, somente atualizar os arquivos no `remote` e, no github.com, criar a build e atualizar o Pages.

#### Primeira opção

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

#### Segunda opção

No terminal do seu computador, faça

* `git add .`
* `git commit -m "Explicação das edições"`
* `git push`

Agora, vá até o repositório online em github.com e faça

* Na guia Actions, seleciona `deploy-book`
* Clique em *Run workflow*
* Na janela, selecione o branch `main`
* Clique em *Run workflow*

## Editando no github.com

No repositório online, você pode criar novos arquivos e editar os arquivos que já existem. Ao final de cada edição, será necessário fazer o commit da edição. Por fim, quando desejar publicar as edições, faça

* Na guia Actions, seleciona `deploy-book`
* Clique em *Run workflow*
* Na janela, selecione o branch `main`
* Clique em *Run workflow*