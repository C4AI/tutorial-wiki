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
│
├─── 3_InstalacaoConfiguracao
│
├─── 4_ContasNaWiki
│
├─── 5_EscrevendoNaWiki
│
├─── Imagens
│
└─── _build
    ├─── .doctrees
    │
    └─── html
```

* O arquivo `Introducao.md` é a primeira página da documentação.
* O arquivo `logo.png` é a logo que aparece no canto superior esquerdo da documentação
* Este arquivo `README.md` explica sobre o repositório e sobre as ferramentas usadas
* O arquivo `requirements.txt` possui pacotes que são necessários para executar códigos usados ao longo do livro. Como este livro serve somente para documentação, não há código e, portanto, o único requisito é o próprio `jupyter-book`
* O arquivo `_config.yml` possui configurações como título do livro, autor, arquivo de logo e opções relacionadas ao github
* O arquivo `toc.yml` possui a estrutura da Table Of Contents (TOC) do livro e o formato dele, que, no caso, é um livro
* A pasta `SobreMediaWiki` contém explicações sobre o MediaWiki em si
* A pasta `InstalacaoConfiguracao` contém explicações sobre a instalação e configuração do MediaWiki
* A pasta `EscrevendoNaWiki` contém explicações com tutoriais mais aplicados para escrita na wiki
* A pasta `Imagens` possui as imagens utilizadas no livro
* A pasta `build` possui a subpasta `html`, que é a versão compilada para *web* do livro, a qual está no Github Pages

## Contribuindo com o tutorial

Para contribuir com o tutorial, consulte as [instruções de contribuição](CONTRIBUTING.md).
