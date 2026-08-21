# Template LaTeX estilo Overleaf para GitHub

Este repositorio funciona como um modelo simples de projeto LaTeX para escrever artigos, monografias, relatorios, dissertacoes ou teses usando GitHub.

A ideia e parecida com o Overleaf:

1. `main.tex` e o arquivo principal.
2. `config/` concentra pacotes, formatacao, metadados e comandos.
3. `capitulos/` guarda os textos chamados pelo `main.tex`.
4. `figuras/` guarda imagens.
5. `tabelas/` guarda tabelas em arquivos separados.
6. `bibliografia/referencias.bib` guarda as referencias.
7. `.github/workflows/latex.yml` compila o PDF automaticamente no GitHub Actions.

## Como usar

1. Clique em `Use this template` no GitHub.
2. Crie um novo repositorio a partir deste modelo.
3. Edite `config/metadados.tex` com titulo, autor, instituicao e data.
4. Escreva os capitulos em `capitulos/`.
5. Coloque imagens em `figuras/`.
6. Cadastre referencias em `bibliografia/referencias.bib`.
7. Faça commit e push.
8. Abra a aba `Actions` para baixar o PDF compilado.

## Estrutura

```text
.
|-- main.tex
|-- config/
|   |-- pacotes.tex
|   |-- formatacao.tex
|   |-- metadados.tex
|   `-- comandos.tex
|-- elementos/
|   |-- pre-textuais.tex
|   `-- pos-textuais.tex
|-- capitulos/
|   |-- 01_introducao.tex
|   |-- 02_metodologia.tex
|   |-- 03_resultados.tex
|   `-- 04_conclusao.tex
|-- figuras/
|   `-- .gitkeep
|-- tabelas/
|   `-- exemplo_tabela.tex
|-- bibliografia/
|   `-- referencias.bib
`-- .github/workflows/latex.yml
```

## Edicao principal

O arquivo `main.tex` chama todos os blocos do projeto. Para adicionar um novo capitulo, crie um arquivo em `capitulos/` e adicione uma linha no `main.tex`:

```tex
\input{capitulos/05_novo_capitulo}
```

## Figuras

Salve imagens em `figuras/` e chame no texto:

```tex
\begin{figure}[htbp]
  \centering
  \includegraphics[width=0.8\textwidth]{figuras/minha_figura.png}
  \caption{Titulo da figura.}
  \label{fig:minha_figura}
\end{figure}
```

## Bibliografia

Adicione referencias em `bibliografia/referencias.bib`:

```bibtex
@article{silva2024,
  author  = {Silva, Joao},
  title   = {Titulo do artigo},
  journal = {Revista Exemplo},
  year    = {2024}
}
```

Depois cite no texto:

```tex
\cite{silva2024}
```

## Compilacao local

Se tiver LaTeX instalado:

```bash
latexmk -pdf main.tex
```

ou:

```bash
pdflatex main.tex
biber main
pdflatex main.tex
pdflatex main.tex
```

## Compilacao no GitHub

A cada `push`, o GitHub Actions executa a compilacao. O PDF fica disponivel nos artefatos da execucao em `Actions`.

## Personalizacao rapida

1. Edite `config/pacotes.tex` para incluir ou remover pacotes.
2. Edite `config/formatacao.tex` para margens, espacamento e cabecalhos.
3. Edite `config/metadados.tex` para informacoes do documento.
4. Edite `config/comandos.tex` para macros reutilizaveis.

