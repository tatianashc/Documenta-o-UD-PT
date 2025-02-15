# Guidelines das guidelines UD-PT

Fluxo de trabalho para preparação da Documentação UD em português (e para língua portuguesa)

* [Como começar](#como-começar)
* [Para enviar alterações](#para-enviar-alterações)
* [Para atualizar a documentação](#para-atualizar-a-documentação)
* [Guidelines](#guidelines)
    * [Chapter, section, subsection, label, caption e fullref](#chapter-section-subsection-label-caption-e-fullref)
    * [Aspas e itálico](#aspas-e-itálico)
    * [Citações](#citações)
    * [Maiúsculas e minúsculas](#maiúsculas-e-minúsculas)
    * [Representação de sentenças](#representação-de-sentenças)


## Como começar

1) **Seguir** o repositório para receber os [**issues**](https://github.com/alvelvis/Documenta-o-UD-PT/issues) por e-mail:

[![Seguir no GitHub](https://img.shields.io/github/watchers/alvelvis/Documenta-o-UD-PT.svg?style=social)](https://github.com/alvelvis/Documenta-o-UD-PT/watchers)

2) Criar um **fork** do repositório:

[![Criar ramificação no GitHub](https://img.shields.io/github/forks/alvelvis/Documenta-o-UD-PT.svg?style=social)](https://github.com/alvelvis/Documenta-o-UD-PT/fork)

3) Instalar o [Git (Windows)](https://git-scm.com/downloads) e **clonar** a *sua* versão do repositório:

```
git clone https://github.com/{username}/Documenta-o-UD-PT
```

4) Instalar o [MiKTeX](https://miktex.org/download) e editar o arquivo **main.tex** com o compilador **XeLaTeX**.

## Para enviar alterações

1) Adicionar todas as alterações feitas ao próximo commit:

```
git add -u
```

2) Realizar **commit** das suas alterações:

```
git commit -m "sobre o que é o commit #número_do_issue_se_houver"
```

3) Continuar realizando outros commits *OU* Enviar as alterações para a *sua* versão do repositório:

```
git push
```

4) Enviar as alterações para a versão oficial do repositório:

[![Enviar PR no GitHub](https://img.shields.io/github/issues-pr/alvelvis/Documenta-o-UD-PT.svg?style=social)](https://github.com/alvelvis/Documenta-o-UD-PT/pulls)

## Para atualizar a documentação

1) Baixar alterações da *sua* versão do repositório (caso esteja trabalhando em computadores diferentes, por exemplo):

```
git pull
```

2) Baixar alterações da versão oficial do repositório:

```
git pull https://github.com/alvelvis/Documenta-o-UD-PT
```

## Guidelines

### Chapter, section, subsection, label, caption e fullref

1) Adicionar **label** para todas as tabelas, figuras, frases, capítulos, seções e subseções, e **caption** para todas as tabelas, figuras e frases, no formato:

```LaTeX
\label{tab/fig/dep/sec:nome}
\caption{}
```

Exemplo:

```LaTeX
\label{fig:example}
\caption{Figura ilustrativa}
```

2) **Captions** de frases e nomes de **chapters**/**sections**/**subsections** devem ter a expressão em foco em itálico:

```LaTeX
\caption{João \emph{começou a fazer} o dever de casa}
```

```LaTeX
\subsection{Verbo \emph{ser} como verbo pleno}
```

3) Adicionar referência para todas as tabelas, figuras, frases, seções e subseções:

```LaTeX
Como na \fullref{fig:example}, ...
```

Resultado: `Como na Figura 1: Figura ilustrativa, ...`

4) **Não** adicione ponto final nos captions para que ele possa ser lido como referência.

### Aspas e itálico

1) **Não** utilizar aspas na documentação, pois elas não são decodificadas pelo LaTeX. Substituir pelo comando *say*:

```LaTeX
\say{Citação importante de um filósofo}
```

Resultado: `"Citação importante de um filósofo"`

2) Utilizar \say{aspas} para palavras e lemas que quero representar, e \emph{itálico} para as outras anotações (pos, deprel, etc.):

```LaTeX
Apenas os verbos \say{ser} e \say{estar} são considerados verbos de ligação, e portanto serão sempre anotados como \emph{AUX}.
```

Resultado: Apenas os verbos "ser" e "estar" são considerados verbos de ligação, e portanto serão sempre anotados como *AUX*.

- Exceto no caso de **caption** e **chapters**/**section**/**subsection**, como visto na [Seção Chapter, section, subsection, label, caption e fullref](#chapter-section-subsection-label-caption-e-fullref), pois o LaTeX não aceita aspas dentro desses lugares, portanto deixamos em itálico as palavras que queremos destacar, e não com aspas.

### Citações

1) Citações devem seguir o nome no arquivo **localbibliography.bib**, por exemplo:

```
@inproceedings{mcdonald2013universal,
  title={Universal dependency annotation for multilingual parsing},
  author={McDonald, Ryan and Nivre, Joakim and Quirmbach-Brundage, Yvonne and Goldberg, Yoav and Das, Dipanjan and Ganchev, Kuzman and Hall, Keith and Petrov, Slav and Zhang, Hao and Oscar, T and others},
  booktitle={Proceedings of the 51st Annual Meeting of the Association for Computational Linguistics (Volume 2: Short Papers)},
  pages={92--97},
  year={2013}
}
```

Como citar:

1) `\citep{mcdonald2013universal}`

2) `\citet{mcdonald2013universal}`

Resultado 1: `(McDonald et al. 2013)`

Resultado 2: `McDonald et al. 2013`

### Maiúsculas e minúsculas

1) Colunas UD são representadas em minúsculas (upos, deprel, etc.)

2) upos são maiúsculas (VERB, AUX, etc.)

3) deprel são minúsculas (ccomp, xcomp, etc.)

### Representação de sentenças

1) Sentenças ideais que representam algum fenômeno podem ser desenhadas utilizando o pacote `tikz-dependency`, cortando a sentença para caber horizontalmente na página.

2) Sentenças de anotação complexa devem ter uma imagem da anotação completa.
